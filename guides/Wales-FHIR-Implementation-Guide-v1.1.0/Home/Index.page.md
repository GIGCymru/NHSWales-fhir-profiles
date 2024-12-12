---
igversion: 2.0.0
---

# Wales FHIR Implementation Guide v{{variable: igversion}} STU2 <a class="btn btn-primary justify-content-md-center" href="#resourceindex" role="button" background-color="21305f">Scroll to resource index</a>

<div class="warning"><b>Important:</b> This is the v{{variable: igversion}} Standard for Trial use (STU2) release of the Data Standards Wales FHIR Implementation Guide. Please be aware that these pages refer to a mixture of active/draft/experimental assets as well as clinical scenarios that are undergoing review.</div>



## Project Description and Scope

<div class="container-fluid">
<div class="row">
	<div class="col">
This Implementation Guide contains the HL7 FHIR R4 standards for use by Health and Care organisations in Wales. The Data Standard Wales profiles have been developed with NHS Wales systems in mind and are derived from the UK Core STU2 v2.0.1 release. All relevant NHS Wales Data Standards have been implemented as appropriate.
<br></br>
These pages contain guidance on the following areas:
<br></br>

<ul class="list-group">
<li>FHIR resource profiles and extensions</li>
<li>FHIR terminology components including ValueSets, CodeSystems and ConceptMaps</li>
<li>Example FHIR resources</li>
<li>Other general guidance useful to FHIR implementers in Wales</li>
</ul>

</div>
	<div class="col">
			<div class="col-md-7 card text-center ">
  <div class="card-body">
    <h4 class="card-title"><b>{{pagelink:Home/Help-and-Support/Related-Pages.page.md,text: Related Pages}}</b></h4>
    <p class="card-text">Links related to NHS Wales FHIR development and UK Core</p>
	</div>
	</div>
			<div class="col-md-7 card text-center">
  <div class="card-body">
    <h4 class="card-title"><b>{{pagelink:Home/Help-and-Support/Version-Control-and-Ballot-Process.page.md}}</b></h4>
    <p class="card-text">Outline of how active, draft, and experimental resources should be handled by implementers</p>
				</div>
				</div>
				<div class="col-md-7 card text-center">
				  <div class="card-body">
    <h4 class="card-title"><b>{{pagelink:Home/Help-and-Support/Help-and-Support.page.md,text: Help and Support}}</b></h4>
    <p class="card-text">For suggestions or queries, please email Data Standards Wales using the link on this page</p>
		</div>
			</div>
			</div>
		</div>
	</div>

### Resource Index

<table id="resourceIndex" class="table table-striped">
  <thead>
    <tr>
      <th scope="col" colspan="2">People</th>
      <th scope="col" colspan="2">Entities</th>
      <th scope="col" colspan="2">Workflow</th>
    </tr>
  </thead>
	<tbody>
		<tr>
      <td class="resource">{{pagelink:DataStandardsWales-Patient}} </td> 
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>
      <td class="resource">{{pagelink:DataStandardsWales-Location}} </td> 
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>	 
      <td class="resource">{{pagelink:DataStandardsWales-Encounter}}  </td> 
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></div></td>	  
    </tr>
    <tr>
      <td class="resource">{{pagelink:DataStandardsWales-Practitioner}} </td>
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>
      <td class="resource">{{pagelink:DataStandardsWales-Organization}}  </td> 
	  <td class=status"><a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>
    </tr>
    <tr>
	  <td class="resource">{{pagelink:DataStandardsWales-PractitionerRole}} </td> 
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>
	  <td class="resource">{{pagelink:DataStandardsWales-Questionnaire}}  </td>
	  <td class=status"><a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
    </tr>
	<tr>
		<td class="resource">{{pagelink:DataStandardsWales-RelatedPerson}}  </td> 
		<td class=status"><a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
		<td class="resource">{{pagelink:DataStandardsWales-QuestionnaireResponse}} </td> 
		<td class=status"> <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
    </tr>
	</tbody>
</table>

<table id="resourceIndex" class="table table-striped">
  <thead>
    <tr>
      <th scope="col" colspan="2">Diagnostics</th>
      <th scope="col" colspan="2">Medication</th>
      <th scope="col" colspan="2">Allergy</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="resource">{{pagelink:DataStandardsWales-ServiceRequest}}  </td> 
	  <td class=status">	  <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
      <td class="resource">{{pagelink:DataStandardsWales-Medication}}  </td> 
	  <td class=status"><a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>
      <td class="resource">{{pagelink:DataStandardsWales-AllergyIntolerance}}  </td>
	  <td class=status"><a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>
	</tr>
	<tr>
	  <td class="resource">{{pagelink:DataStandardsWales-DiagnosticReport}} </td> 
	  <td class=status">  <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
      <td class="resource">{{pagelink:DataStandardsWales-MedicationAdministration}}  </td> 
	  <td class=status"><a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>
	  <td class="resource">{{pagelink:DataStandardsWales-AllergyList}} </td> 
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>
	</tr>
	<tr>
	  <td class="resource">{{pagelink:DataStandardsWales-DiagnosticReport-Lab}}  </td>
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
	  <td class="resource">{{pagelink:DataStandardsWales-MedicationDispense}}  </td> 
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>
	</tr>
	<tr>
	  <td class="resource">{{pagelink:DataStandardsWales-Observation}} </td> 
	  <td class=status">  <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
	  <td class="resource">{{pagelink:DataStandardsWales-MedicationList}} </td> 
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>
	</tr>
	<tr>
		<td class="resource">{{pagelink:DataStandardsWales-Observation-VitalSigns}}  </td>
		<td class=status"> <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
		<td class="resource">{{pagelink:DataStandardsWales-MedicationRequest}} </td>
		<td class=status"> <a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>
	</tr>
  <tr>
	<td class="resource">{{pagelink:DataStandardsWales-Observation-VitalSigns-BodyHeight}}  </td>
	<td class=status"> <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
	<td class="resource">{{pagelink:DataStandardsWales-MedicationStatement}}  </td> 
	<td class=status"><a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Active</a></td>
	</tr>
	<tr>
	  <td class="resource">{{pagelink:DataStandardsWales-Observation-VitalSigns-BMI}}  </td>
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
	  <td class="resource">{{pagelink:DataStandardsWales-Dosage}}  </td>
	  <td class=status"><a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Draft</a></td>
	</tr>
	<tr>
  	  <td class="resource">{{pagelink:DataStandardsWales-Observation-VitalSigns-BodyWeight}} </td> 
	  <td class=status">  <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
	  <td class="resource">{{pagelink:DataStandardsWales-Immunization}} </td>
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagactive" target="_blank">Draft</a></td>
	</tr>
	<tr>
	  <td class="resource">{{pagelink:DataStandardsWales-Observation-Lab}}  </td> 
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
	</tr>
	<tr>
	  <td class="resource">{{pagelink:DataStandardsWales-Specimen}}  </td>
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
	</tr>
	<tr>
	  <td class="resource">{{pagelink:DataStandardsWales-ImagingStudy}}  </td>
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
	</tr>
	<tr>
	  <td class="resource">{{pagelink:DataStandardsWales-Endpoint}} </td>
	  <td class=status">  <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
	</tr>
	<tr>
		<td class="resource">{{pagelink:DataStandardsWales-Device}}  </td> 
		<td class=status"> <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
    </tr>
  </tbody>
</table>

<table id="resourceIndex" class="table table-striped" style="width:34%">
  <thead>
    <tr>
      <th scope="col" colspan="2">Security and Privacy</th>
    </tr>
  </thead>
  <tbody>
	</tr>
	<tr>
	  <td class="resource" style="width:74%">{{pagelink:DataStandardsWales-AuditEvent}} </td>
	  <td class=status">  <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
	</tr>
	<tr>
      <td class="resource">{{pagelink:DataStandardsWales-Provenance}}  </td> 
	  <td class=status"> <a href="/ui/workflow/overview?id=1" class="tagdraft" target="_blank">Draft</a><div class="tagexperimental tt">E<span class="tooltiptext">Experimental profile</span></td>
    </tr>
  </tbody>
</table>