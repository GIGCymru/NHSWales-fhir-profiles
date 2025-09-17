---
name: DataStandardsWalesImmunizationRecommendation
---

## {{page-title}}

The [Immunization Recommendation](https://www.hl7.org/fhir/r4/immunizationrecommendation.html) resource is intended to cover communication of a specified patient's immunization recommendations and status across all healthcare disciplines in all care settings and all regions. The set of customized (for the patient) recommendations is based on the comparison of the patient's immunization history with a set of published recommendations (protocols).

Additionally, the Immunization Recommendation resource is expected to cover key concepts related to the querying of a patient's immunization recommendations and status.

The {{page-title}} profile is derived from the [HL7 International Immunization Recommendation Profile](https://www.hl7.org/fhir/R4/immunizationrecommendation.html). It defines additional rules for use within health and care organisations in Wales.

A direct link to the Data Standards Wales asset can be accessed here - {{link:https://fhir.nhs.wales/fhir/StructureDefinition/DataStandardsWales-ImmunizationRecommendation}}

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
      {{tree:https://fhir.nhs.wales/fhir/StructureDefinition/DataStandardsWales-ImmunizationRecommendation, snapshot}}
    </div>
    <div id="tabdiff" class="tabcontent">
      {{tree:https://fhir.nhs.wales/fhir/StructureDefinition/DataStandardsWales-ImmunizationRecommendation, diff}}
  </div>
    <div id="tabhybrid" class="tabcontent">
      {{tree:https://fhir.nhs.wales/fhir/StructureDefinition/DataStandardsWales-ImmunizationRecommendation, hybrid}}
  </div>
  <div id="tabeg" class="tabcontent">
  </div>    
</div>

---

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements
Refer to the {{pagelink:Home/Introduction/Profile-Descriptions/Mandatory-and-Must-Support-Data-Elements.page.md,text: Mandatory and Must Support}} page for guidance on how these elements should be interpreted.

Each Immunization Recommendation **must have**:

|Element|Reason|
|-|-|
|`ImmunizationRecommendation.patient`|The patient for whom the immunisation was recommended.|
|`ImmunizationRecommendation.date`|The date on which the recommendation was made.|
|`ImmunizationRecommendation.recommendation`|The nature of the recommendation.|
|`ImmunizationRecommendation.recommendation.forecastStatus`|Indicates the patient status with respect to the path to immunity for the target disease, e.g. due, complete, immune, or contraindicated.|