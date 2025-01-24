<div class="col-md-6 guidancesidepanel">
{{index:Home/API-Guidance}} 
</div>
 
<div class="col-md-18">

<div class="warning"><b>Important:</b> All content in this FHIR Implementation Guide is under development</div>

## {{page-title}}

### Overview
The following Profile defined as part of the [Data Standards Wales implementation guide](https://simplifier.net/guide/fhir-standards-wales-implementation-guide?version=current){target="_blank"}:

 - [DataStandardsWales-DiagnosticReport](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-DiagnosticReport.page.md?version=current){target="_blank"}

This page describes how the DataStandardsWales DiagnosticReport profiles can support the three types of reports that would be returned against a patient within NHS Wales.

### Report Types
DataStandards Wales DiagnosticReport support three types of reports. 

- Query for patient DiagnosticReport returning Laboratory Results
- Query for patient DiagnosticReport returning Imaging Study Result
- Query for patient DiagnosticReport returning result with attached document

Additional and more detailed guidance can be found at [Diagnostic Report Guidance page](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/Guidance/Diagnostic-Reports?version=current){target="_blank"} in the [Data Standards Wales implementation guide](https://simplifier.net/guide/fhir-standards-wales-implementation-guide?version=current){target="_blank"}


### Security Labels
DataStandards Wales DiagnosticReport support using Security Labels for identifying DiagnosticReports as **highly sensitive**. Additional and more detailed guidance can be found at [Sensitive Data Guidance page](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/Guidance/Sensitive-Data?version=current){target="_blank"} in the [Data Standards Wales implementation guide](https://simplifier.net/guide/fhir-standards-wales-implementation-guide?version=current){target="_blank"}

### BasedOn
References the ServiceRequest where that information is available in WRRS.

### Status

| WRRS Status | DiagnosticReport Status |
| -- | -- |
| A/F | Final |
| C | Cancelled |
| I | Partial |
| P | Registered |
| R | Preliminary |
| U | Amended |
| Default | Unknown |

### Category
- Set to the WRRS ProviderType Code
- https://fhir.nhs.wales/Id/wrrs-provider-type-code


### Code
- https://fhir.nhs.wales/Id/wrrs-provider-system-code

### Example Diagnostic Report - Pathology Full Blood Count

<div class="tab-wrap">
  <ul class="tab-head">
    <li class="tablink" onclick="openCity(this,'tabtree')" data-target="tabtree">
      Overview
    </li>
    <li class="tablink" onclick="openCity(this,'tabtable')" data-target="tabtable">
      Table
    </li>
    <li class="tablink tab-active" onclick="openCity(this,'tabxml')" data-target="tabxml">
      XML
    </li>    
    <li class="tablink" onclick="openCity(this,'tabjson')" data-target="tabjson">
      JSON
    </li>    
    <li class="tablink" onclick="openCity(this,'tabnarrative')" data-target="tabnarrative">
      Narrative
    </li>
  </ul>
  <div class="tab-main">
    <div id="tabtree" class="tabcontent">
      {{tree:Example-DataStandardsWales-DiagnosticReport-FullBloodCount}}
    </div>
    <div id="tabtable" class="tabcontent">
      {{table:Example-DataStandardsWales-DiagnosticReport-FullBloodCount}}
    </div>       
    <div id="tabxml" class="tabcontent active">      
      {{xml:Example-DataStandardsWales-DiagnosticReport-FullBloodCount}}
    </div>
    <div id="tabjson" class="tabcontent">
      {{json:Example-DataStandardsWales-DiagnosticReport-FullBloodCount}}
    </div>       
    <div id="tabnarrative" class="tabcontent">
      {{narrative:Example-DataStandardsWales-DiagnosticReport-FullBloodCount}}
    </div>  
  </div>
</div>

<br />

</div>
