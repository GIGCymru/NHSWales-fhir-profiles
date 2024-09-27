---
name: DataStandardsWalesPatient
---

## {{page-title}}


### FQL

@```
    from
        StructureDefinition
    where
        name='DataStandardsWalesPatient'
    select 
        Profile: name,
        Type: type,
        Status: status,
        Canonical: url
```

{{page:Home/FHIR-Assets/Profiles-and-Extensions/ResourceOverview.page.md}}



# StructureDefinition-UKCore-Patient

<div id="transpose">
@```
from
	StructureDefinition
where
	name = 'DataStandardsWalesPatient'
select
	Canonical_URL: url,
  Current_Version: version,
  Last_Updated: date,
	Description: description
```
</div>
<br>
@```
from
	StructureDefinition
where
	name = 'DataStandardsWalesPatient'
select
	Profile_Purpose: purpose
```

<nocheck>
<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
   <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree: snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree: diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table: snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml: snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json: snapshot}}
</div>

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>Richard Smith</b> - An example to illustrate a male patient's demographics. 
</br>
{{pagelink:Example-UKCore-Patient-RichardSmith}}   
<br><br>
 
</div>
</nocheck>

### Example Usage Scenarios ###
The following are example usage scenarios for the UK Core Patient profile:

- Query for Patient demographic information using the query parameter `Patient.identifier` for a known NHS number.
- Query for Patient demographic information using query parameters such as `Patient.name.family`, `Patient.name.given`, `Patient.birthDate`, and `Patient.gender`.
- Exchange Patient demographic information within a FHIR document or message.

---

## Profile Specific Implementation Guidance: ##

### Mandatory and Must Support Data Elements

The following elements are identified as MustSupport, and it is expected that consumers and suppliers SHALL support these as per the {{pagelink:Guidance-MustSupport-25267}}.

<table class="assets">
<tr>
<th width="30%">Element</th>
<th width="70%">Reason</th>
</tr>
<tr>
<td><code>Patient.identifier</code></td>
<td>An identifier for this patient.</td>
</tr>
<tr>
<td><code>Patient.active</code></td>
<td>Whether this patient's record is in active use.</td>
</tr>
<tr>
<td><code>Patient.name</code></td>
<td>A name associated with the patient.</td>
</tr>
<tr>
<td><code>Patient.telecom</code></td>
<td>A contact detail for the individual</td>
</tr>
<tr>
<td><code>Patient.gender</code></td>
<td> the gender that the patient is considered to have for administration and record keeping purposes.</td>
</tr>
<tr>
<td><code>Patient.birthDate</code></td>
<td>The date of birth for the individual.</td>
</tr>
<tr>
<td><code>Patient.address</code></td>
<td>An address for the individual</td>
</tr>
</table>

---
