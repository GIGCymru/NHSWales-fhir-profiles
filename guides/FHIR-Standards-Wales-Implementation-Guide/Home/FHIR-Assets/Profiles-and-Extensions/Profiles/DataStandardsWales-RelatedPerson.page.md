<div class="warning"><span class="ImplementWarn"></span></div>

## {{page-title}}

### Overview
The [RelatedPerson](https://www.hl7.org/fhir/r4/relatedperson.html) resource is about the information about a person that is involved in the care for a patient, but who is not the target of healthcare, nor has a formal responsibility in the care process.

The {{page-title}} profile is derived from the [UK Core RelatedPerson Profile](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-RelatedPerson?version=current). It defines additional rules for use within health and care organisations in Wales.

A direct link to the Data Standards Wales asset can be accessed here - {{link:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-RelatedPerson}}


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
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-RelatedPerson, snapshot}}
    </div>
    <div id="tabdiff" class="tabcontent">
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-RelatedPerson, diff}}
  </div>
    <div id="tabhybrid" class="tabcontent">
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-RelatedPerson, hybrid}}
  </div>
  <div id="tabeg" class="tabcontent">
    <list>
      <li>{{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Profiles/Examples/Example-DataStandardsWales-RelatedPerson-NaturalMother.page.md, text:Example Related Person - Natural Mother}}</li>
    </list>
  </div>   
</div>

### Mandatory and Must Support Data Elements
Refer to the {{pagelink:Home/Introduction/Profile-Descriptions/Mandatory-and-Must-Support-Data-Elements.page.md,text: Mandatory and Must Support}} page for guidance on how these elements should be interpreted.

The following elements are defined by [Core Reference Data Standards](https://www.datadictionary.wales.nhs.uk/#!WordDocuments/corereferencedatastandards1.htm), which are also marked as must be supported:

* postcode
* title
