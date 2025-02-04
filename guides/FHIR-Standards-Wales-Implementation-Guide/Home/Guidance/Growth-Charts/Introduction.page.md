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
* {{pagelink:DataStandardsWales-Encounter,text:Encounter}} 
* {{pagelink:DataStandardsWales-Observation,text:Observation}}
* {{pagelink:DataStandardsWales-Observation-VitalSigns,text:Observation-Vital Signs}}
* {{pagelink:DataStandardsWales-Observation-VitalSigns-BMI,text:Observation-Vital Signs-BMI}}
* {{pagelink:DataStandardsWales-Observation-VitalSigns-BodyHeight,text:Observation-Vital Signs-Body Height}}
* {{pagelink:DataStandardsWales-Observation-VitalSigns-BodyWeight,text:Observation-Vital Signs-Body Weight}}
* {{pagelink:DataStandardsWales-Patient,text:Observation}}
* {{pagelink:DataStandardsWales-Practitioner,text:Practitioner}}
* {{pagelink:DataStandardsWales-PractitionerRole,text:Practitioner Role}}
* {{pagelink:DataStandardsWales-Questionnaire,text:Questionnaire}}
* {{pagelink:DataStandardsWales-QuestionnaireResponse,text:Questionnaire Response}}
* {{pagelink:DataStandardsWales-RelatedPerson,text:Related Person}}


<br>

{{render:Diagrams-growth-chart-simplified-logical-model}}

<br>


## FHIR Resources

### Encounter
To link a growth chart measurement event to a specific encounter, the `Encounter.class` has been linked to a SNOMED code for Growth Chart (record artifact).

### Observation - Vital Signs

The Observation - Vital Signs profile and its children, are used for specific observations linked to measurements taken from the patient or someone related to the patient. In the context of growth charts, it includes the following:

* {{pagelink:DataStandardsWales-Observation-VitalSigns,text:Data Standards Wales Observation-Vital Signs Profile}} - included here is Head Circumference.
  * {{pagelink:DataStandardsWales-Observation-VitalSigns-BMI,text:Data Standards Wales Observation-Vital Signs-BMI Profile}}
  * {{pagelink:DataStandardsWales-Observation-VitalSigns-BodyHeight,text:Data Standards Wales Observation-Vital Signs-Body Height Profile}}  - including that of the parents of the child
  * {{pagelink:DataStandardsWales-Observation-VitalSigns-BodyWeight,text:Data Standards Wales Observation-Vital Signs-Body Weight Profile}}


### Observation 
{{pagelink:DataStandardsWales-Observation,text:Data Standards Wales Observation Profile}} is for any other observation that is not considered a vital sign. We have, in this context, Bone Age, which is a parameter or measure taken from an X-Ray and not from the patient themselves. 

Bone age has then been classified as an `Observation` resource with `Observation.category` of "Imaging".

<br>

{{render:Diagrams-LogicalModel-growthChart-ObservationGroup}}

<br>


### Practitioner
No deviation from the standard guidance. 

### Questionnaire
{{pagelink:DataStandardsWales-Questionnaire,text:Data Standards Wales Questionnaire Profile}} is used here to capture information about the patient's condition (currently either Turner or Down syndrome). 


### QuestionnaireResponse
Each time a user selects a type of patient condition, an instance conforming to the {{pagelink:DataStandardsWales-QuestionnaireResponse,text:Data Standards Wales Questionnaire Response Profile}} is created, which is linked to the corresponding {{pagelink:DataStandardsWales-Questionnaire,text:Questionnaire}}. 

The QuestionnaireResponse contains information about notable patient conditions, such as Down syndrome or Turner syndrome. This selection determines which graph is presented to the user for plotting measurements.


### Related Person
A {{pagelink:DataStandardsWales-RelatedPerson,text:Related Person}} could be anyone connected to the patient. In this case, it is particularly relevant for parents or carers of the child, as they may occasionally provide data for the growth chart.

The role of {{pagelink:DataStandardsWales-RelatedPerson,text: Data Standards Wales Related Person Profile}} is also significant when referencing Mid-Parental Height. This measure, derived from the natural mother and father’s heights, uses the {{pagelink:DataStandardsWales-Observation-VitalSigns-BodyHeight,text:Data Standards Wales Observation-Vital Signs-Body Height Profile}} as the base. Here, the `subject` is the patient (i.e., the child), and the `focus` is set to the 'natural mother' or 'natural father'.

<br>

{{render:Diagrams-LogicalModel-growthChart-MidParentalHeight}}

<br>

## Measures taken by parents or carers
A child’s height or weight may be measured by parents or carers who have received training from healthcare professionals. In this instance the `Observation.performer` for a specific measurement would reference {{pagelink:DataStandardsWales-RelatedPerson,text: a Related Person}} to accurately record the contributor of the measurement.

## Use of QuestionnaireResponse instead of Condition

Although it is highly likely that a patient's conditions are formally recorded elsewhere, we currently do not have access to that data. 

In this use case, conditions such as Down syndrome or Turner syndrome might be noted during form completion; however, key details—such as the author, date of diagnosis, and verification status—are not captured. Without this critical information, these records do not constitute a formal diagnostic entry.. 

Additionally, the terminology used is overly broad and fails to differentiate between subtypes (e.g., complete trisomy 21 versus mosaic trisomy 21), each of which would require its own SNOMED CT code. This granularity is unavailable at this point within this context.

Our recommendation is to use a {{pagelink:DataStandardsWales-Questionnaire,text:Questionnaire}} and a {{pagelink:DataStandardsWales-QuestionnaireResponse,text:Questionnaire Response}} to record the information for now. When such data becomes available from other systems within the CDR, appropriate mapping will be necessary. 


