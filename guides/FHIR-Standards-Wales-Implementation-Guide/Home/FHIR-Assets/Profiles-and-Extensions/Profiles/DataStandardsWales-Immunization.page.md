---
name: DataStandardsWalesImmunization
---

## {{page-title}}

The [Immunization](https://www.hl7.org/fhir/r4/immunization.html) resource is a record of the immunization received by a patient, often in the form of a vaccine.

The {{page-title}} profile is derived from the [UK Core Immunization Profile](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU2/Home/ProfilesandExtensions/Profile-UKCore-Immunization?version=2.0.1). It defines additional rules for use within health and care organisations in Wales.

A direct link to the Data Standards Wales asset can be accessed here - {{link:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Immunization}}

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
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Immunization, snapshot}}
    </div>
    <div id="tabdiff" class="tabcontent">
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Immunization, diff}}
  </div>
    <div id="tabhybrid" class="tabcontent">
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-Immunization, hybrid}}
  </div>
  <div id="tabeg" class="tabcontent">

- {{pagelink:ImmunizationFluVaccine, text: Example Immunization - Flu Vaccine}} Query for a Flu Vaccination using query parameters such as `Immunization.extension:vaccinationProcedure`, `Immunization.vaccineCode` and `Immunization.reasonCode`.
- {{pagelink:ImmunizationNotGiven, text: Example Immunization - Not Given}} Query for a vaccine that was not given using query parameters such as `Immunization.status` and `Immunization.statusReason`.
- {{pagelink:ImmunizationParentPresent, text: Example Immunization - Parent Present}} Query for a vaccination injection given to a paediatric patient with a parent/carer present using query parameters such as `Immunization.extension:parentPresent`, `Immunization.lotNumber` and `Immunization.expirationDate`.

_*Examples provided have been clinically assured on the 07-Aug-2024_
  </div>    
</div>

---

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements
Refer to the {{pagelink:Home/Introduction/Profile-Descriptions/Mandatory-and-Must-Support-Data-Elements.page.md,text: Mandatory and Must Support}} page for guidance on how these elements should be interpreted.

Each Immunization **must have**:

|Element|Reason|
|-|-|
|`Immunization.status`|Will generally be set to show that the immunisation has been completed or not done.|
|`Immunization.vaccineCode`|Vaccine product administered.|
|`Immunization.patient`|The patient who either received or did not receive the immunisation.|
|`Immunization.occurrence[x]`|Date vaccine administered or was to be administered.|


Each Immunization **must support**:

|Element|Reason|
|-|-|
|`Immunization.identifier`|A unique identifier assigned to this immunisation record.|
|`Immunization.statusReason`|Indicates the reason the immunization event was not performed.|
|`Immunization.recorded`|When the immunisation was first captured in the subject's record.|
|`Immunization.reportOrigin`|Indicates the source of a secondarily reported record.|
|`Immunization.location`|The service delivery location where the immunisation administration occurred.|
|`Immunization.manufacturer`|Name of vaccine manufacturer.|
|`Immunization.lotNumber`|Lot number of the vaccine product.|
|`Immunization.expirationDate`|Date vaccine batch expires.|
|`Immunization.site`|Body site where vaccine was administered.|
|`Immunization.route`|The path by which the vaccine product is taken into the body.|
|`Immunization.doseQuantity`|The quantity of vaccine product that was administered.|
|`Immunization.performer`|Indicates who performed the immunization event.|
|`Immunization.reasonCode`|Reasons why the vaccine was administered.|
|`Immunization.protocolApplied`|The protocol being followed by the provider who administered the dose.|

### Extensions

The extensions listed below allow a number of the data elements listed above to be supported where not currently supported by the FHIR standard:

* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Extensions/Extension-DataStandardsWales-AdministeredProduct.page.md,text:DataStandardsWales-AdministeredProduct}}
* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Extensions/Extension-DataStandardsWales-DateProcedureLastUpdated.page.md,text:DataStandardsWales-DateProcedureLastUpdated}}
* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Extensions/Extension-DataStandardsWales-ForecastCreationSource.page.md,text:DataStandardsWales-ForecastCreationSource}}
* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Extensions/Extension-DataStandardsWales-Immunization.basedOn.page.md,text:DataStandardsWales-Immunization.basedOn}}

