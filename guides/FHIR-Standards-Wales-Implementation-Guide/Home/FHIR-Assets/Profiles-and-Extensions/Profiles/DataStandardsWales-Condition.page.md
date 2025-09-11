<div class="warning"><span class="ImplementWarn"></span></div>

## {{page-title}}

### Overview
The [Condition](https://www.hl7.org/fhir/R4/condition.html) resource describes a clinical condition, problem, diagnosis, or other event, situation, issue, or clinical concept that has risen to a level of concern. 

The {{page-title}} 
profile is derived from the [UK Core Condition Profile](https://simplifier.net/guide/uk-core-implementation-guide-stu2/Home/ProfilesandExtensions/Profile-UKCore-Condition). It defines additional rules for use within health and care organisations in Wales. 

A direct link to the Data Standards Wales asset can be accessed here - {{link:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Condition}}

### Formal Views of Profile Content
<div class="tab-wrap">
  <ul class="tab-head">
    <li class="tablink tab-active" onclick="openCity(this,'tabsnap')" data-target="tabsnap">
      Snapshot View
    </li>
    <li class="tablink" onclick="openCity(this,'tabdiff')" data-target="tabdiff">
      Differential View
    </li>
    <li class="tablink" onclick="openCity(this,'tabhybrid')" data-target="tabhybrid">
      Hybrid View
    </li>
    <li class="tablink" onclick="openCity(this,'tabeg')" data-target="tabeg">
      Examples
    </li>
  </ul>
  <div class="tab-main">
    <div id="tabsnap" class="tabcontent active">      
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Condition, snapshot}}
    </div>
    <div id="tabdiff" class="tabcontent">
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Condition, diff}}
  </div>
    <div id="tabhybrid" class="tabcontent">
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Condition, hybrid}}
  </div>
  <div id="tabeg" class="tabcontent">
     Examples are currently under development.
  </div>
</div>

### Mandatory and Must Support Data Elements
Refer to the {{pagelink:Home/Introduction/Profile-Descriptions/Mandatory-and-Must-Support-Data-Elements.page.md,text: Mandatory and Must Support}} page for guidance on how these elements should be interpreted.

Each Condition record must have:
* A `Condition.subject` to indicate the patient or group with whom the condition record is associated.

Each Condition record must support:
* A `Condition.clinicalStatus` to indicate the clinical status of the condition.
* A `Condition.verificationStatus` to indicate whether and how the clinical status of the condition is verified.
* A `Condition.severity` to indicate a subjective assessment of the severity of the condition as evaluated by the clinician.
* A `Condition.code` to indicate the identity of the condition, problem or diagnosis..
* A `Condition.recorder` to indicate the individual who recorded the record and takes responsibility for its content.
