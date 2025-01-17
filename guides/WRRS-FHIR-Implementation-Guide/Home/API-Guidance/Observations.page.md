<div class="col-md-6 guidancesidepanel">
{{index:Home/API-Guidance}} 
</div>
 
<div class="col-md-18">

<div class="warning"><b>Important:</b> All content in this FHIR Implementation Guide is under development</div>


## {{page-title}}

### Overview
The following Profile defined as part of the [Data Standards Wales implementation guide](https://simplifier.net/guide/fhir-standards-wales-implementation-guide?version=current){target="_blank"}:

 - [DataStandardsWales-Observation](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-Observation.page.md?version=current){target="_blank"}

### Observation Groups and Results

#### Logical Model
The diagram below shows the typical relationship between NHS Wales Observation groups and results.
<br>

{{render:D-LogicalModel-DiagnosticReport-MultiplePanel-UreaElectrolytes.drawio}}

<br />

#### Context
Where the DiagnosticReport includes multiple panels of results these results will be grouped, as **hasMember** references, by the Observation Group Observation as described in the diagram above. The Observation group does not include the results but gives you the authorized information and the requested profile. The DiagnosticReport will include one or multiple references to the Obervation groups as Results.


### Identifiers

| Resource | Naming System | 
| -- | -- | 
| Observation Group | https://fhir.nhs.wales/Id/wrrs-obr-identifier | 
| Observation Result | https://fhir.nhs.wales/Id/wrrs-obx-identifier | 


### Security Labels
DataStandards Wales Observation support using Security Labels for identifying Observations as **highly sensitive**. Additional and more detailed guidance can be found at [Sensitive Data Guidance page](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/Guidance/Sensitive-Data?version=current){target="_blank"} in the [Data Standards Wales implementation guide](https://simplifier.net/guide/fhir-standards-wales-implementation-guide?version=current){target="_blank"}

### Code

The Observation supports search against:

- https://fhir.nhs.wales/Id/wrrs-test-code (eg. ACE)
- https://fhir.nhs.wales/Id/lims-test-code (eg. B3503)
- http://read.info/readv2 (eg. 44CH.)
- http://snomed.info/sct (eg. 999681000000101)

```
get [host]/Observation?&patient=Patient/NN046351-149&code=https://fhir.nhs.wales/Id/wrrs-test-code|ACE
get [host]/Observation?&patient=Patient/NN046351-149&code=https://fhir.nhs.wales/Id/lims-test-code|B3503
get [host]/Observation?&patient=Patient/NN046351-149&code=http://read.info/readv2|44CH.
get [host]/Observation?&patient=Patient/NN046351-149&code=http://snomed.info/sct|999681000000101

```

### $LastN
Please see the [$LastN PLugin](https://simplifier.net/guide/WRRS-FHIR-Implementation-Guide/Home/Guidance/LastN-Plugin.page.md?version=current) guidance page for more information on searching Observation results by $LastN.

### Examples

#### Example Observation Group - Pathology Liver Function Test

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
      {{tree:Example-DataStandardsWales-ObservationGroup-LFT}}
    </div>
    <div id="tabtable" class="tabcontent">
      {{table:Example-DataStandardsWales-ObservationGroup-LFT}}
    </div>       
    <div id="tabxml" class="tabcontent active">      
      {{xml:Example-DataStandardsWales-ObservationGroup-LFT}}
    </div>
    <div id="tabjson" class="tabcontent">
      {{json:Example-DataStandardsWales-ObservationGroup-LFT}}
    </div>       
    <div id="tabnarrative" class="tabcontent">
      {{narrative:Example-DataStandardsWales-ObservationGroup-LFT}}
    </div>  
  </div>
</div>

<br />

#### Example Observation Result - Pathology Whole Blood Count

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
      {{tree:Example-DataStandardsWales-ObservationResult-FBC_WBC}}
    </div>
    <div id="tabtable" class="tabcontent">
      {{table:Example-DataStandardsWales-ObservationResult-FBC_WBC}}
    </div>       
    <div id="tabxml" class="tabcontent active">      
      {{xml:Example-DataStandardsWales-ObservationResult-FBC_WBC}}
    </div>
    <div id="tabjson" class="tabcontent">
      {{json:Example-DataStandardsWales-ObservationResult-FBC_WBC}}
    </div>       
    <div id="tabnarrative" class="tabcontent">
      {{narrative:Example-DataStandardsWales-ObservationResult-FBC_WBC}}
    </div>  
  </div>
</div>

<br />

</div>