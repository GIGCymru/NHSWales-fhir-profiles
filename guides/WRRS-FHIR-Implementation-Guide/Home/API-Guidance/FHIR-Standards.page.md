<div class="col-md-6 guidancesidepanel">
{{index:Home/API-Guidance}} 
</div>
 
<div class="col-md-18">

<div class="warning"><b>Important:</b> All content in this FHIR Implementation Guide is under development</div>


# {{page-title}}

## Overview
The response messages from the API conform to the Data Standards Wales profiles published and maintained as part of the [Data Standards Wales Implementation Guide](https://simplifier.net/guide/fhir-standards-wales-implementation-guide?version=current). Information and links to relevant resources are profile guidance used as part of this work is found below.

## FHIR Profiles

**The following Profiles have been defined as part of the [Data Standards Wales implementation guide](https://simplifier.net/guide/fhir-standards-wales-implementation-guide?version=current).** Links below are references to the Data Standards Wales profiles. <u>There are currently no project specific profiles in place.</u>

Diagnostics resources also reference profiles such as [Organisation](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-Organization.page.md?version=current){target="_blank"} and [Patient](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-Patient.page.md?version=current){target="_blank"}. Profile standards and guidance for all resources referenced in this Implementation Guide can be found in the [Data Standards Wales Implementation Guide](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home?version=current){target="_blank"}.

| Profile | Guidance |
| --
| [DataStandardsWales-DiagnosticReport](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-DiagnosticReport.page.md?version=current){target="_blank"} <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a>| [Data Standards Wales DiagnosticReport Guidance](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/Guidance/Diagnostic-Reports?version=current){target="_blank"} |
| [DataStandardsWales-DiagnosticReport-Lab](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-DiagnosticReport-Lab.page.md?version=current){target="_blank"} <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a>| [Data Standards Wales DiagnosticReport Guidance](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/Guidance/Diagnostic-Reports?version=current){target="_blank"} |
 | [DataStandardsWales-Endpoint](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-Endpoint.page.md?version=current){target="_blank"} <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a>| |
 | [DataStandardsWales-ImagingStudy](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-ImagingStudy.page.md?version=current){target="_blank"} <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a>| |
 | [DataStandardsWales-Observation-Lab](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-Observation-Lab.page.md?version=current){target="_blank"} <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a>| |
 | [DataStandardsWales-ServiceRequest](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-ServiceRequest.page.md?version=current){target="_blank"} <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a>| |
 | [DataStandardsWales-Specimen](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-Specimen.page.md?version=current){target="_blank"} <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a>| |

## Extensions

| Extension | Details |
|--
| [Extension-UKCore-CodingSCTDescId](https://simplifier.net/guide/HL7FHIRUKCoreR4Release1/Home/ProfilesandExtensions/ExtensionLibrary?version=current#ExtensionUKCore-CodingSCTDescId){target="_blank"}  | Used as part of the Observation Laboratory Profile result, This extension extends the Coding datatype to support the exchange of the selected description ID and display term for a SNOMED CT concept, which is currently not supported by the FHIR standard. |

## Security
Please refer to the [Sensitive data](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/Guidance/Sensitive-Data?version=current) guidance page in Data Standards Wales for details on using the http://terminology.hl7.org/CodeSystem/v3-Confidentiality codesystem within Diagnostic resources.

## Naming Systems

The [Naming Systems](https://hl7.org/fhir/namingsystem.html){target="_blank"}  used as part of this FHIR API conform to the Data Standards Wales Naming Systems published as part of [Data Standards Wales Implementation Guide](https://simplifier.net/guide/fhir-standards-wales-implementation-guide?version=current).
</div>
