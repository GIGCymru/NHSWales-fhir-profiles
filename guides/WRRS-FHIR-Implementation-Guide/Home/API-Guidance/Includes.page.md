<div class="col-md-6 guidancesidepanel">
{{index:Home/API-Guidance}} 
</div>
 
<div class="col-md-18">

<div class="warning"><b>Important:</b> All content in this FHIR Implementation Guide is under development</div>


## {{page-title}}

https://www.hl7.org/fhir/search.html#revinclude

## Overview
The following Profiles defined as part of the [Data Standards Wales implementation guide](https://simplifier.net/guide/fhir-standards-wales-implementation-guide?version=current) support include and revinclude logic:

 - [DataStandardsWales-ServiceRequest](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-ServiceRequest.page.md?version=current){target="_blank"}
 - [DataStandardsWales-DiagnosticReport](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-DiagnosticReport.page.md?version=current){target="_blank"}
 - [DataStandardsWales-Observation](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-Observation.page.md?version=current){target="_blank"}

## Include
Clients may request that the engine return resources related to the search results, in order to reduce the overall network delay of repeated retrievals of related resources. This is useful when the client is searching on a clinical resource, but for every such resource returned, the client will also need the subject (patient) resource that the clinical resource refers to. The client can use the [_include](http://hl7.org/fhir/R4/search.html#include){target="_blank"} parameter to indicate that the subject resources be included in the results.

### Supported

| Resource | Field | Included Resource |
| -- | -- | -- |
| DiagnosticReport | subject | Patient |
| DiagnosticReport | result | Observation |
| DiagnosticReport | performer | Organization |
| ServiceRequest | subject | Patient |
| Observation | subject | Patient |


### Examples

#### ServiceRequest
- Get servicerequest by multiple Subject Identifiers, include subject (Patient resource) in result bundle.

```
ServiceRequest?subject:Patient.identifier=https://fhir.hduhb.nhs.wales/Id/pas-identifier|NN046351,https://fhir.nhs.wales/Id/lims-identifier|206180&_include=ServiceRequest:Subject
```
- Get servicerequest by PAS Identifier, include subject (Patient resource) in result bundle.
```
ServiceRequest?subject:Patient.identifier=https://fhir.hduhb.nhs.wales/Id/pas-identifier|NN046351&_include=ServiceRequest:Subject
```

#### Observation
- Get Observation by multiple Subject Identifiers, include subject (Patient resource) in result bundle.
```
Observation?subject:Patient.identifier=https://fhir.hduhb.nhs.wales/Id/pas-identifier|NN046351,https://fhir.nhs.wales/Id/lims-identifier|206180&_include=Observation:subject
```
- Get Observation by PAS Identifier, include subject (Patient resource) in result bundle.
```
Observation?subject:Patient.identifier=https://fhir.hduhb.nhs.wales/Id/pas-identifier|NN046351&_include=Observation:subject
```

## RevInclude
An alternative scenario to **_include** is where the client wishes to fetch a particular resource, and any resources that refer to it. For example, the client may wish to fetch a Patient, and any Observation resources where the patient is the subject. This is known as a reverse include, and is specified by providing a [_revinclude](http://hl7.org/fhir/R4/search.html#revinclude){target="_blank"} parameter.

### Supported

| Resource | Field | Included Resource |
| -- | -- | -- |
| Patient | subject | Observation |
| Patient | subject | ServiceRequest |
| Patient | subject | DiagnosticReport |
| Patient | subject | Specimen |

### Examples
- Patient by ID, revinclude Observations where the Patient is the subject.
```
Patient?_id=NN046351-149&_revinclude=Observation:subject
```
- Patient by ID, revinclude Observations where the Patient is the subject.
```
Patient/NN046351-149?_revinclude=Observation:subject
```
- Patient by PAS Identifier, revinclude Observations where the Patient is the subject.
```
Patient?identifier=https://fhir.hduhb.nhs.wales/Id/pas-identifier|NN046351,https://fhir.nhs.wales/Id/lims-identifier|206180&_revinclude=Observation:subject
```
