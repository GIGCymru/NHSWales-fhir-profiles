<div class="warning"><span class="ExperiWarn"></span></div>

## {{page-title}}

### Overview
The [Encounter-UEC](https://www.hl7.org/fhir/r4/encounter.html) resource is used to describe a patient’s attendance at a healthcare facility for Urgent and Emergency Care.

The {{page-title}} profile is derived from the [NHS Wales Encounter Profile]({{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-Encounter.page.md}}) and is therefore listed as experimental. It defines additional rules for use within Urgent and Emergency Care uses in health and care organisations in Wales.

Refer to [Digital Health and Care Wales Welsh Emergency Care Data Set User Guide v0.1](https://dhcw.nhs.wales/data/information-standards/data-standards/data-standards-files/20250123-wecds-user-guide-v1-00-final-published-pdf/) for additional guidance.

A direct link to the Data Standards Wales asset can be accessed here - {{link:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Encounter-UEC}}

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
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Encounter-UEC, snapshot}}
    </div>
    <div id="tabdiff" class="tabcontent">
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Encounter-UEC, diff}}
  </div>
    <div id="tabhybrid" class="tabcontent">
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Encounter-UEC, hybrid}}
  </div>
  <div id="tabeg" class="tabcontent">
  Examples are currently under development.
  </div>    
</div>

### Mandatory and Must Support Data Elements
Refer to the {{pagelink:Home/Introduction/Profile-Descriptions/Mandatory-and-Must-Support-Data-Elements.page.md,text: Mandatory and Must Support}} page for guidance on how these elements should be interpreted.
 
Each Encounter must have:
1. A status
1. A class (e.g. inpatient, emergency etc)

Each Encounter must support:
1. An identifier
1. A subject
1. Participant(s) in the encounter
1. Hospitalization information
1. Admission source
1. Discharge destination
1. Admission method *
1. Discharge method *
1. Emergency care discharge status *
1. Outcome of attendance *

_*see Implementation Guidance on UK Core extensions for the Encounter resource below_

The `Encounter.status` field **SHALL** be populated with one of the following values defined by the FHIR standard:  
  * planned 
  * arrived
  * triaged
  * in-progress
  * onleave
  * finished
  * cancelled
  * entered-in-error
  * unknown
<br><br>
The `Encounter.class` field **SHALL** be populated using the values defined by the FHIR standard

### Extensions
The extensions listed below allow a number of the data elements listed above to be supported where not currently supported by the Data Standards Wales Encounter profile:
* Data Standards Wales Extensions:
    * {{pagelink:Extension-DataStandardsWales-UEC-ExpectedTimeOfTreatment}} supports recording of the time of treatment expected at the point of referral.
    * {{pagelink:Extension-DataStandardsWales-UEC-DischargeInformationGiven}} supports recording of secondary information at UEC Discharge, and whether this was given to the patient.
    * {{pagelink:Extension-DataStandardsWales-UEC-AttendanceCategory}} supports recording of the reporting category of each attendance.
* HL7 International Extensions:
    * [Encounter Mode Of Arrival](https://hl7.org/fhir/R4/extension-encounter-modeofarrival.html) supports recording of the mode of arrival of the patient.
<br><br>
