---
topic: GrowthChart-FHIR-Data-Model
---

# {{page-title}}

<div style="float:right;border:1px;border-style:solid;padding:10px;margin:10px;width:300px;">

  - [Data Model Overview](#data-model-overview)
  - [FHIR Resources](#fhir-resources)
    * [Encounter](#encounter)
    * [Observation](#observation)
    * [Observation - Vital Signs](#observation-vital-signs)
    * [Practitioner Role](#practitioner-role)
    * [Questionnaire](#questionnaire)
    * [QuestionnaireResponse](#questionnaireresponse)
    * [Related Person](#related-person)
    * [Administrative resources](#administrative-resources)
  - [Measures taken by parents or carers](#measures-taken-by-parents-carer)
</div>

## Data Model Overview
The Growth Chart project utilises FHIR resources to streamline the collection of paediatric growth data. Some of the information included in the growth charts are height, weight, BMI, head circumference, bone age and certain conditions. 
Specific profiles have been developed to represent these growth related observations and administrative details, such as encounter or practitioner role. 

The diagram below gives an overview of what FHIR resources are needed and how they are linked together.

The FHIR data model consists of the following resources: 
* Encounter
* Observation 
* Observation - Vital Signs
* Patient
* Organization
* Practitioner
* Location
* Questionnaire
* QuestionnaireResponse

For the CarePlan, Task and QuestionnaireResponse resources, specific PSOM profiles are created to capture elements of the Clinical Circumstance as well as the Collection Event, while several PSOM-specific Questionnaire instances have been created which represent the different PROMs Tools. The Patient, Practitioner, Organization and Location resources are based on existing Data Standards Wales Profiles and are used to capture administrative metadata.

{{render:guides/DataStandardsWalesPSOM/Home/Guidance/Images/DataModel.png}}

The responsibility for creating and populating resources in the data model is divided between the Health Board and the PROMs provider. The Health Board is responsible for generating the CarePlan, Task, Patient, Practitioner and Organization instances. The PROMs provider is responsible for creating the Task, QuestionnaireResponse, Organization and Location instances. Each party populates different elements of the metadata.

Note however that the above only specifies which party is **initially** responsible for populating the relevant elements. Both parties should be able to update existing resources, for instance whenever a PROM has been completed, the PROMs provider should be able to update the corresponding Task resource accordingly.

## FHIR Resources

### Encounter
The {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Encounter.page.md}} profile represents a patient's attendance or meeting with a healthcare professional, often in a healthcare facility (although it can also be a domicilary visit, for example). Each CarePlan resource is used to group Collection Events and provides context by specifying the Pathway Type, the Referral ID and the Treatment Specialty.

The CarePlan may also point to resources that hold information on a patient's planned or performed appointments and performed procedures. This clinical-related information may function as a trigger for the PROMs provider to determine the appropriate scheduling of PROMs collection.
The Originating Organisation is mapped to the `.identifier.assigner` of the CarePlan, as it plays an organising function throughout the Clinical Circumstance and provides the content of the CarePlan. The Senior Responsible Professional is the author of the CarePlan. This professional has responsibility for the patient within the pathway.

The PSOM CarePlan profile is derived from the [UK Core CarePlan profile](https://simplifier.net/hl7fhirukcorer4/ukcore-careplan).

### Observation
A Collection Event serves as a trigger to prompt a patient to complete one or more PROMs Tools and to collect their answers and scores. Each instance conforming to the {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation.page.md}} profile represents a PROMs Tool within a Collection Event. The Task is linked to from the CarePlan resource and contains input, such as a link to the Questionnaire that needs to be filled in, and output, i.e. a QuestionnaireResponse. The PROMs Trigger Event Type and the Event Location Code are also collected here.

The PSOM Task profile is derived from the [UK Core Task profile](https://simplifier.net/hl7fhirukcorer4/ukcore-task).

### Observation - Vital Signs

{{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation-VitalSigns.page.md}}

### Practitioner Role
{{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-PractitionerRole.page.md}}

### Questionnaire
{{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Questionnaire.page.md}}

In the context of both DSCNs and LPDSs, the representation of a PROMs is manifested through a dedicated Questionnaire instance. The corresponding terminology resources are created using ValueSet and CodeSystem resources, which are linked within the Questionnaire instances. Furthermore, the Questionnaire consists of a structured set of questions that guide the collection of answers according to the DSCN/LPDS specifications.

The primary purpose of representing PROMs Tools as Questionnaire instances is to establish a canonical identifier for each PROMs Tool in the form of a URI. This URI serves as a linkage point connecting Tasks and QuestionnaireResponses to their corresponding Questionnaires. 

Please note that, within the current PSOM data model design, the Questionnaire resource is not technically indispensable for the generation of a QuestionnaireResponse. Nevertheless, leveraging Questionnaire instances for PROMs Tools offers a significant advantage in terms of standardised and structured formatting. Each question within the Tool is encapsulated within the Questionnaire, uniquely identified by the Question Reference mapped to the `.item.linkId` elements. Moreover, the terminology used in the PROMs Tools has been represented in FHIR ValueSet and CodeSystem resources and is bound to the correct questions in the Questionnaire. This allows access to all definitions in a programmer-friendly manner.

It is important to note that the Questionnaire instances provide limited capabilities around rendering in the user interface of the PROMs provider platform. For example, the instances do not provide instructions on how questions should be displayed or how users should navigate through them. Refer to the PSOM-DSCN User Guide for further information on Questionnaire rendering.

### QuestionnaireResponse
Each time a patient completes a PROMs Tool, an instance conforming to the {{pagelink:Home/FHIR-Artefacts/Profiles-and-Extensions/DataStandardsWales-PSOM-QuestionnaireResponse.page.md}} profile is created, which represents a structured collection of answers to the corresponding Questionnaire. The PROMs provider provides the QuestionnaireResponse with an identifier and designates itself as the `.identifier.assigner`. The QuestionnaireResponse also contains the calculated scores, completion date and the language of the completed form. A Health Board can also use the same QuestionnaireResponse instance obtained from the PROMs provider, along with the additional metadata items required in the CarePlan, to flow the national collection of PROMs (i.e aligned to a DSCN) into NDR.

The PSOM QuestionnaireResponse profile is derived from the [UK Core QuestionnaireResponse profile](https://simplifier.net/hl7fhirukcorer4/ukcore-questionnaireresponse).

The diagram below is an example of how the CarePlan, Task, Questionnaire and QuestionnaireResponse are tied together in the context of Collection Events. The (content of the) Data Entry Questionnaire is explained in more detail below. 

{{render:guides/DataStandardsWalesPSOM/Home/Guidance/Images/Proxyfilling.jpg}}


### Related Person

### Administrative resources
The administrative metadata is captured using the Patient and Practitioner resources. For these resources, the Data Standards Wales FHIR profiles are reused, and there is no specific guidance required.

## Measures taken by parents or carers
In certain situations, a patient may not be able to independently complete questionnaires, necessitating the involvement of a proxy, such as a family member or consultant. It is imperative for Health Boards to ensure that the information on who completed the questionnaires is accessible when analysing the responses obtained from the questionnaires. 

The Data Entry Questionnaire is one of the Questionnaires scheduled within each collection event that allows to gather this type of information. It contains questions that capture specific details about the individual who completed the questionnaires. The answers for the Data Entry Questionnaire are only collected at the beginning of a new collection event. A collection event consists of one or more pathway-specific questionnaires, in addition to the Data Entry Questionnaire. It is expected that the PROMs provider will include, at a minimum, the QuestionnaireResponse for the Data Entry Questionnaire per collection event in the response to the Health Board. In addition to the aforementioned approach, the PROMs provider could further optimise by extracting the responses related to proxy completion and populate `QuestionnaireResponse.source` and `QuestionnaireResponse.author`.

As discussed in PSOM FHIR Data Model, every Task is linked to one Questionnaire. The answers are collected in a QuestionnaireReponse that is linked to the respective Task resource. All Tasks within one collection event share the same value for `.reasonCode` and `.input:triggerEventDate`. These values establish a distinctive combination that creates a coherent link between the outcomes of the Data Entry Questionnaire and the other questionnaires within a collective event.