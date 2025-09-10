<div class="warning"><span class="ExperiWarn"></span></div>

## {{page-title}}
The [DocumentReference](https://www.hl7.org/fhir/r4/documentreference.html) resource profile is used to index a document, clinical note, or other binary object to make them available to a healthcare system. A document is some sequence of bytes that is identifiable, establishes its own context (e.g., what subject, author, etc. can be displayed to the user), and has defined update management. The DocumentReference resource can be used with any document format that has a recognized mime type and that conforms to this definition.

The {{page-title}} profile is derived from the [HL7 R4 DocumentReference](https://www.hl7.org/fhir/r4/documentreference.html). It defines additional rules for use within health and care organisations in Wales.

A direct link to the Data Standards Wales asset can be accessed here - {{link:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-DocumentReference}}

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
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-DocumentReference, snapshot}}
    </div>
    <div id="tabdiff" class="tabcontent">
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-DocumentReference, diff}}
  </div>
    <div id="tabhybrid" class="tabcontent">
      {{tree:https://fhir.nhs.wales/StructureDefinition/DataStandardsWales-DocumentReference, hybrid}}
  </div>
  <div id="tabeg" class="tabcontent">

  </div>
</div>

### Mandatory and Must Support Data Elements
Refer to the {{pagelink:Home/Introduction/Profile-Descriptions/Mandatory-and-Must-Support-Data-Elements.page.md,text: Mandatory and Must Support}} page for guidance on how these elements should be interpreted.
 
Each DocumentReference must have:
1. A status
1. One or more attachments as *either* a base 64 binary *or* a URL. 

Each Encounter must support:
1. One or more identifiers
1. A document status
1. A type
1. One or more categories
1. A subject
1. A date
1. One or more authors
1. An authenticator
1. A custodian
1. One or more security labels
<br><br>

The `DocumentReference.status` field **SHALL** be populated with a value from [HL7 FHIR Document Reference Status](http://hl7.org/fhir/ValueSet/document-reference-status|4.0.1)
<br><br>

The `DocumentReference.docStatus` field **SHALL** be populated with a value from [HL7 FHIR Document Composition Status](http://hl7.org/fhir/ValueSet/composition-status|4.0.1)
<br><br>

### Extensions
The extensions listed below allow a number of the data elements listed above to be supported where not currently supported by the FHIR standard: 
  * {{pagelink:Extension-DataStandardsWales-DocumentAttribute}} supports the capture of a value from {{pagelink:ValueSet-DataStandardsWales-DocumentAttribute}}.
  * {{pagelink:Extension-DataStandardsWales-DigitalStatus}} supports the capture of a value from {{pagelink:ValueSet-DataStandardsWales-DigitalStatus}}
  * {{pagelink:Extension-DataStandardsWales-DocumentRepository}} supports the capture of the repository in which a document reference is stored by reference to an instance of the {{pagelink:DataStandardsWales-Device}} resource profile
