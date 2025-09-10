<div class="warning"><span class="ImplementWarn"></span></div>

## {{page-title}}

### Overview
The [Appointment](https://www.hl7.org/fhir/r4/Appointment.html) resource primarily allows the recording of detailed information about a planned meeting that may be in the future or past. The resource only describes a single meeting, a series of repeating visits would require multiple appointment resources to be created for each instance.

The {{page-title}} profile is derived from the [UK Core Appointment Profile](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU2/Home/ProfilesandExtensions/Profile-UKCore-Appointment?version=2.0.1). It defines additional rules for use within health and care organisations in Wales.

A direct link to the Data Standards Wales asset can be accessed here - {{link:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Appointment}}

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
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Appointment, snapshot}}
    </div>
    <div id="tabdiff" class="tabcontent">
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Appointment, diff}}
  </div>
    <div id="tabhybrid" class="tabcontent">
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Appointment, hybrid}}
  </div>
  <div id="tabeg" class="tabcontent">
    <list>
      <li>{{pagelink:Example-DataStandardsWales-Appointment-GenSurgery, text:Example Appointment - General Surgery}}</li>        
    </list>
  </div>    
</div>


