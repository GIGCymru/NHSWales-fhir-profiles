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
The Growth Chart project utilises FHIR resources to streamline the collection of paediatric growth data. Some of the information included in the growth charts are height, weight, BMI, head circumference, bone age and certain conditions. 
Specific profiles have been developed to represent these growth related observations and administrative details, such as encounter or practitioner role. 

The diagram below gives an overview of what FHIR resources are needed and how they are linked together.

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
The {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Encounter.page.md}} profile represents a patient's attendance or meeting with a healthcare professional, often in a healthcare facility (although it can also be a domiciliary visit, for example). 

To link a growth chart measurement event to a specific encounter, the 'Encounter.class' has been linked to a SNOMED code for Growth Chart (record artifact).

The Encounter profile is derived from the [UK Core Encounter Profile](https://simplifier.net/guide/uk-core-implementation-guide-stu2/Home/ProfilesandExtensions/Profile-UKCore-Encounter?version=2.0.1).

### Observation - Vital Signs

The Observation - Vital Signs resource is for specific observations that are linked to measures around the patient. In the context of growth chart we have included the following:

* {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation-VitalSigns.page.md}} - included here is Head Circumference
* {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation-VitalSigns-BMI.page.md}}
* {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation-VitalSigns-BodyHeight.page.md}} - including that of the parents of the child)
* {{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation-VitalSigns-BodyWeight.page.md}}


### Observation 
{{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Observation.page.md}} is for any other observation that is not considered a vital sign. We have, in this context, Bone Age, which is a parameter or measure taken from an X-Ray and not from the patient themselves. 

Bone age is been then classified as an 'Observation' resource with 'Observation.category' of 'Imaging' 

{{render:Diagrams\LogicalModel-growthChart-Observation group.png}}


### Practitioner
A practitioner in FHIR is any health and care professional that is involved in the care of a patient or citizen. 

In this context, and many more, often healthcare professional without a professional registration (e.g. Healthcare support workers) will be the ones taking measurements, observations and will be the authors of documentation. 
Therefore, for these users, there is an option of capturing their Nadex as part of 'Practitioner.identifier'.
{{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-PractitionerRole.page.md}}

### Questionnaire
{{pagelink:Home\FHIR-Assets\Profiles-and-Extensions\Profiles\DataStandardsWales-Questionnaire.page.md}} is used here to capture information about the patient's condition (currently either Turner's or Down syndrome). 

### QuestionnaireResponse
Each time a user completes selects a type of patient condition, an instance conforming to the {{pagelink:Home/FHIR-Artefacts/Profiles-and-Extensions/DataStandardsWales-PSOM-QuestionnaireResponse.page.md}} profile is created, which is linked to the corresponding Questionnaire. 
The QuestionnaireResponse contains information around a notable condition of the patient such as Down Synfrome or Turner's syndrome. If neither are selected, UK WHO is the answer. The selection of a condition (or no selection) will inform which graph to present to the user where the measurements are plotted. 

### Related Person
A related person could be anybody that has a link with the patient. In this instance it was particularly relevant for parents or carers of the child, since they will be occassionally the authors of the data inputted in the growth chart. 

It is relevant to mention as well the role of RelatedPerson when referencing for Mid-Parental Height. For this measure, derived from the mother and father's height, we have utilised an Observation - Vital Sign - Body Height resource as the base with special mention to 'subject' being the patient (aka the child) and 'focus' being set to 'natural mother' or 'natural father'. 

{{render:Diagrams\LogicalModel-growthChart-Mid parental height.png}}

## Measures taken by parents or carers
The child's height or weight might be measured by the parents or carer of the patient after receiving training from healthcare professionals. 
This is important to capture on the form because, although the author of the form itself might be a health and care professional, the 'Observation.performer' for that particular measurement will be a reference to 'RelatedPerson'.

## Use of QuestionnaireResponse instead of Condition
Not enough data is captured to have a veridic condition list, for example at the point of the form Down syndrome or Turner syndrome might be captured, but we wouldn’t know author, date of diagnosis being made or the verification status (currently only being captured as ‘provisional’ although that hasn’t been confirmed by a clinician). 
Furthermore, those two components are too wide, and it does not differentiate between the different down syndrome for example (complete trisomy 21 vs mosaic trisomy 21). Those two different genetic conditions, need two separate SNOMED codes but we wouldn’t know at that point which one is.

Our recommendation is to proceed with a questionnaire (more below) and capture a complete condition information in future development, where a condition will be entered correctly, data maintained by the appropriate clinician and removed when required. Some mapping will be required in the future. 
