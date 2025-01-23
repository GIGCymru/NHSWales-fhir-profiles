<div class="col-md-6 guidancesidepanel">
{{index:Home/API-Guidance}} 
</div>
 
<div class="col-md-18">

<div class="warning"><b>Important:</b> All content in this FHIR Implementation Guide is under development</div>

## {{page-title}}

### Overview
The following Profiles defined as part of the [Data Standards Wales implementation guide](https://simplifier.net/guide/fhir-standards-wales-implementation-guide?version=current) support searching and sorting by date:

 - [DataStandardsWales-ServiceRequest](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-ServiceRequest.page.md?version=current){target="_blank"}
 - [DataStandardsWales-DiagnosticReport](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-DiagnosticReport.page.md?version=current){target="_blank"}
 - [DataStandardsWales-Observation](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-Observation.page.md?version=current){target="_blank"}


_Implementation Notes:_ 
- [How to sort by date](http://hl7.org/fhir/R4/search.html#sort){target="_blank"}
- [How to search by date](http://hl7.org/fhir/R4/search.html#date){target="_blank"}

### Sorting

#### How sort is evaluated in the FHIR WRRS API:

|Operator | Action |
| --- | --- |
| _sort=authored | Sort Ascending |
| _sort=+authored | Sort Ascending |
| _sort=-authored | Sort Descending |


#### Date Sort fields

|Resource|Property|
| --- | --- |
| [DataStandardsWales-ServiceRequest](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-ServiceRequest.page.md?version=current){target="_blank"} | Authored |
| [DataStandardsWales-DiagnosticReport](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-DiagnosticReport.page.md?version=current){target="_blank"} | Issued |
| [DataStandardsWales-Observation](https://simplifier.net/guide/FHIR-Standards-Wales-Implementation-Guide/Home/FHIR-Assets/Profiles-and-Extensions/Profiles/DataStandardsWales-Observation.page.md?version=current){target="_blank"} | Date |

### Comparison Operators 

https://www.hl7.org/fhir/search.html#prefix

For the ordered parameter types of number, date, and quantity, a prefix to the parameter value may be used to control the nature of the matching. To avoid URL escaping and visual confusion, the following prefixes are used:

|Comparison Operator|Function|
| --- | --- |
|eq|	the value for the parameter in the resource is equal to the provided value|
|gt|	the value for the parameter in the resource is greater than the provided valu|
|lt|	the value for the parameter in the resource is less than the provided value|
|ge|	the value for the parameter in the resource is greater or equal to the provided value|
|le|	the value for the parameter in the resource is less or equal to the provided value|

### Search by date
https://www.hl7.org/fhir/search.html#date


| Operator | Match | No Match |
| --- | --- |
|[parameter]=eq2013-01-14	| 2013-01-14T00:00 matches | 2013-01-15T00:00 does not match - it's not in the range |
|[parameter]=lt2013-01-14T10:00	| 2013-01-14 matches, because it includes the part of 14-Jan 2013 before 10am | 2013-01-15T00:00 does not match - it's not in the range|
|[parameter]=gt2013-01-14T10:00	| 2013-01-14 matches, because it includes the part of 14-Jan 2013 after 10am | 2013-01-13T00:00 does not match - it's not in the range |
|[parameter]=ge2013-03-14	| "from 21-Jan 2013 onwards" is included because that period may include times after 14-Mar 2013 | 2013-01-13T00:00 does not match - it's not in the range |
|[parameter]=le2013-03-14	| "from 21-Jan 2013 onwards" is included because that period may include times before 14-Mar 2013 | 2013-01-15T00:00 does not match - it's not in the range |


### Examples

- Search by patient id, issued within range:
```
GET [base]\DiagnosticReport?subject:Patient._id=NN046351-149&issued=lt2022-05-13T16:12:27+00:00
```
- Search by patient id, issued within range:
```
GET [base]\DiagnosticReport?subject:Patient._id=NN046351-149&issued=lt2022-05-13
```
- Search by patient id, issued within range:
```
GET [base]\DiagnosticReport?subject:Patient._id=NN046351-149&issued=gt2022-05-09T16:12:27+00:00
```
- Search by patient id, issued within range:
```
GET [base]\DiagnosticReport?subject:Patient._id=NN046351-149&issued=gt2022-05-09
```
- Search by patient id, issued within range:
```
GET [base]\DiagnosticReport?subject:Patient._id=NN046351-149&issued=eq2022-05-10T16:12:27+00:00
```
- Search by patient id, issued within range:
```
GET [base]\DiagnosticReport?subject:Patient._id=NN046351-149&issued=eq2022-05-10
```
- Search by patient id, issued within range:
```
GET [base]\DiagnosticReport?subject:Patient._id=NN046351-149&issued=le2022-05-10T16:12:27+00:00
```
- Search by patient id, issued within range:
```
GET [base]\DiagnosticReport?subject:Patient._id=NN046351-149&issued=le2022-05-10
```
- Search by patient id, issued within range:
```
GET [base]\DiagnosticReport?subject:Patient._id=NN046351-149&issued=ge2022-05-10T16:12:27+00:00
```
- Search by patient id, issued within range:
```
GET [base]\DiagnosticReport?subject:Patient._id=NN046351-149&issued=ge2022-05-10
```
- Search by patient id, issued within range:
```
GET [base]\DiagnosticReport?subject:Patient._id=NN046351-149&issued=ge2022-05-10T16:12:27+00:
issued=lt2022-05-13T16:12:27+00:00
```
- Search by patient id, issued within range:
```
GET [base]\DiagnosticReport?subject:Patient._id=NN046351-149&issued=ge2022-05-10&issued=lt2022-05-13
```


#### Scenario 
Get Servicerequest by patient identifier, sort by **authored**

```
GET [base]\ServiceRequest?_sort=-authored&_count=10&subject:Patient.identifier=https://fhir.hduhb.nhs.wales/Id/pas-identifier|NN046351
```

</div>