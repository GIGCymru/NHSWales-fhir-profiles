<div class="col-md-6 guidancesidepanel">
{{index:Home/API-Guidance}} 
</div>
 
<div class="col-md-18">

<div class="warning"><b>Important:</b> All content in this FHIR Implementation Guide is under development</div>


## {{page-title}}

## Overview
The following Profile defined as part of the [Data Standards Wales implementation guide](https://simplifier.net/guide/fhir-standards-wales-implementation-guide?version=current){target="_blank"}:

 - [DataStandardsWales-ServiceRequest](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-ServiceRequest.page.md?version=current){target="_blank"}

A service request can be in a state of request and order. A request occurs when the request is first created and the order is still on its route through integration services.
A service request can also be in a state of ordered where the laboratory systems have accepted the order and begun processing.

### identifiers
Order Item

### Security Labels
DataStandards Wales ServiceRequest supported using Security Labels for identifying ServiceRequests as **highly sensitive**. Additional and more detailed guidance can be found at [Sensitive Data Guidance page](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/Guidance/Sensitive-Data?version=current){target="_blank"} in the [Data Standards Wales implementation guide](https://simplifier.net/guide/fhir-standards-wales-implementation-guide?version=current){target="_blank"}

### Requisition Number
A shared identifier common to all service requests that were authorized more or less simultaneously by a single author, representing the composite or group identifier. More information [here](https://www.hl7.org/fhir/servicerequest-definitions.html#ServiceRequest.requisition){target="_blank"}. The requisition number is set to the WRRS Request number encompassing one or multiple requests/orders.


### Status and Intent
- Status

| WRRS Status | RequestStatus | 
| -- | -- | 
| Active | RequestStatus.Active | 
| Filled | RequestStatus.Completed  | 

- Intent = RequestIntent.Order;

### Category

| ProviderTypeCode | Provider Type | ServiceRequest Category | SnomedCT Code
| -- | -- | -- | -- |
| Pathology | P | Laboratory procedure | 108252007 |
| Radiology | R | Imaging | 363679005 |

### Priority 


| WRRS Priority | Description | RequestPriority | 
| -- | -- | -- | -- |
| U | Urgent | RequestPriority.Urgent | 
| USC | Urgent (Suspected Cancer) | RequestPriority.Urgent | 
| R | Routine | RequestPriority.Routine | 

### Supported Queries

#### Search by ID
```
GET [base]\ServiceRequest/500015292106
```
```
GET [base]\ServiceRequest?_id=500011611601
```

#### Search by PAS Identifier and Include
```
GET [base]\ServiceRequest?subject:Patient.identifier=https://fhir.hduhb.nhs.wales/Id/pas-identifier|NN046351&_include=ServiceRequest:Subject
```

#### Search by subject and authored date

```
GET [base]\ServiceRequest?subject:Patient._id=NN046351-149&authored=lt2022-05-13T16:12:27+00:00
```
```
GET [base]\ServiceRequest?subject:Patient._id=NN046351-149&authored=lt2022-05-13
```
```
GET [base]\ServiceRequest?subject:Patient._id=NN046351-149&authored=gt2022-05-09T16:12:27+00:00
```
```
GET [base]\ServiceRequest?subject:Patient._id=NN046351-149&authored=gt2022-05-09
```
```
GET [base]\ServiceRequest?subject:Patient._id=NN046351-149&authored=eq2022-05-10T16:12:27+00:00
```
```
GET [base]\ServiceRequest?subject:Patient._id=NN046351-149&authored=eq2022-05-10
```
```
GET [base]\ServiceRequest?subject:Patient._id=NN046351-149&authored=le2022-05-10T16:12:27+00:00
```
```
GET [base]\ServiceRequest?subject:Patient._id=NN046351-149&authored=le2022-05-10
```
```
GET [base]\ServiceRequest?subject:Patient._id=NN046351-149&authored=ge2022-05-10T16:12:27+00:00
```
```
GET [base]\ServiceRequest?subject:Patient._id=NN046351-149&authored=ge2022-05-10
```
```
GET [base]\ServiceRequest?subject:Patient._id=NN046351-149&authored=ge2022-05-10T16:12:27+00:00&authored=lt2022-05-13T16:12:27+00:00
```
```
GET [base]\ServiceRequest?subject:Patient._id=NN046351-149&authored=ge2022-05-10&authored=lt2022-05-13
```
### Examples

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
      {{tree:E-Diagnostics-Example-DataStandardsWales-ServiceRequest-RadiologyOrder}}
    </div>
    <div id="tabtable" class="tabcontent">
      {{table:E-Diagnostics-Example-DataStandardsWales-ServiceRequest-RadiologyOrder}}
    </div>       
    <div id="tabxml" class="tabcontent active">      
      {{xml:E-Diagnostics-Example-DataStandardsWales-ServiceRequest-RadiologyOrder}}
    </div>
    <div id="tabjson" class="tabcontent">
      {{json:E-Diagnostics-Example-DataStandardsWales-ServiceRequest-RadiologyOrder}}
    </div>       
    <div id="tabnarrative" class="tabcontent">
      {{narrative:E-Diagnostics-Example-DataStandardsWales-ServiceRequest-RadiologyOrder}}
    </div>  
  </div>
</div>

<br/>
</div>