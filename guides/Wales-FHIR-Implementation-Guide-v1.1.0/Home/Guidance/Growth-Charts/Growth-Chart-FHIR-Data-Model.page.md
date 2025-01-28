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
  - [Measures taken by parents or carers](#measures-taken-by-parents-carer)
  - [Use of QuestionnaireResponse instead of Condition](#use-of-questionnaireresponse-instead-of-condition)
</div>

## Data Model Overview
The Growth Chart project utilises FHIR resources to streamline the collection of paediatric growth data. The charts include key parameters such as height, weight, BMI, head circumference, bone age, and certain conditions.
Specific profiles have been developed to represent growth-related observations and administrative details, such as encounters or practitioner roles.

The diagram below provides an overview of the required FHIR resources and how they are interconnected.

The FHIR data model consists of the following resources: 
* Encounter
* Observation 
* Observation - Vital Signs
* Patient
* Practitioner
* PractitionerRole
* Questionnaire
* QuestionnaireResponse
* RelatedPerson

{{render:Diagrams\growth-chart-simplified-logical-model.png}}


## FHIR Resources

### Encounter
The {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Encounter.page.md}} profile represents a patient's attendance or meeting with a healthcare professional, often in a healthcare facility (although it can also include domiciliary visits). 

To link a growth chart measurement event to a specific encounter, the 'Encounter.class' has been linked to a SNOMED code for Growth Chart (record artifact).

The Encounter profile is derived from the [UK Core Encounter Profile](https://simplifier.net/guide/uk-core-implementation-guide-stu2/Home/ProfilesandExtensions/Profile-UKCore-Encounter?version=2.0.1).

### Observation - Vital Signs

The Observation - Vital Signs resource is used for specific observations linked to measurements taken from the patient or someone related to the patient. In the context of growth charts, it includes the following:

* {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation-VitalSigns.page.md}} - included here is Head Circumference
* {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation-VitalSigns-BMI.page.md}}
* {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation-VitalSigns-BodyHeight.page.md}} - including that of the parents of the child
* {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation-VitalSigns-BodyWeight.page.md}}


### Observation 
{{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation.page.md}} is for any other observation that is not considered a vital sign. We have, in this context, Bone Age, which is a parameter or measure taken from an X-Ray and not from the patient themselves. 

Bone age is been then classified as an 'Observation' resource with 'Observation.category' of 'Imaging' 

The {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation.page.md}} profile is derived from the [UK Core Observation Profile](https://simplifier.net/guide/uk-core-implementation-guide-stu2/Home/ProfilesandExtensions/Profile-UKCore-Observation?version=2.0.1)

{{render:Diagrams\LogicalModel-growthChart-Observation group.png}}


### Practitioner
A {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Practitioner.page.md}}practitioner in FHIR is any health and care professional that is involved in the care of a patient or citizen. 

In many cases, healthcare professionals without a professional registration (e.g., Healthcare Support Workers) may take measurements, make observations, and author documentation. For these users, there is an option to capture their Nadex as part of 'Practitioner.identifier'.
{{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-PractitionerRole.page.md}}

The {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Practitioner.page.md}} profile is derived from the [UK Core Practitioner Profile](https://simplifier.net/guide/uk-core-implementation-guide-stu2/Home/ProfilesandExtensions/Profile-UKCore-Practitioner?version=2.0.1).

### Questionnaire
{{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Questionnaire.page.md}} is used here to capture information about the patient's condition (currently either Turner's or Down syndrome). 

This profile is derived from the [HL7 R4 Questionnaire](https://hl7.org/fhir/R4/questionnaire.html)

### QuestionnaireResponse
Each time a user completes selects a type of patient condition, an instance conforming to the {{pagelink:Home/FHIR-Artefacts/Profiles-and-Extensions/DataStandardsWales-PSOM-QuestionnaireResponse.page.md}} profile is created, which is linked to the corresponding Questionnaire. 

The QuestionnaireResponse contains information about notable patient conditions, such as Down syndrome or Turner syndrome. If neither condition is selected, the default response is UK WHO. This selection determines which graph is presented to the user for plotting measurements.

This profile is derived from the [HL7 R4 Questionnaire](https://hl7.org/fhir/R4/questionnaireresponse.html)

### Related Person
A {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-RelatedPerson.page.md}} could be anyone connected to the patient. In this case, it is particularly relevant for parents or carers of the child, as they may occasionally provide data for the growth chart.

The role of {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-RelatedPerson.page.md}} is also significant when referencing Mid-Parental Height. This measure, derived from the mother’s and father’s heights, uses an Observation - Vital Signs - Body Height resource as the base. Here, the subject is the patient (i.e., the child), and the focus is set to the 'natural mother' or 'natural father'.

This profile is derived from the [UK Core RelatedPerson Profile](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-RelatedPerson?version=current).

{{render:Diagrams\LogicalModel-growthChart-Mid parental height.png}}

## Measures taken by parents or carers
A child’s height or weight may be measured by parents or carers who have received training from healthcare professionals. It is important to capture this on the form, as the author of the form might be a healthcare professional, but the 'Observation.performer' for a specific measurement would reference {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-RelatedPerson.page.md}}.

## Use of QuestionnaireResponse instead of Condition
At this stage, insufficient data is available to create a definitive condition list. For instance, Down syndrome or Turner syndrome might be recorded during form completion, but key details such as the author, date of diagnosis, and verification status are not captured (currently only provisionally marked and unconfirmed by a clinician).

Additionally, these terms are too broad and do not differentiate between subtypes (e.g., complete trisomy 21 vs mosaic trisomy 21), each requiring separate SNOMED codes. This granularity is unavailable at this point.

Our recommendation is to use a {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Questionnaire.page.md}} and {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-QuestionnaireResponse.page.md}} to record the information for now. A more comprehensive condition record can be developed in the future, where data is maintained by the appropriate clinician and updated as needed. Mapping will also be required in later stages.


