<div class="col-md-6 guidancesidepanel">
{{index:Home/API-Guidance}} 
</div>
 
<div class="col-md-18">

<div class="warning"><b>Important:</b> All content in this FHIR Implementation Guide is under development</div>


## {{page-title}}

### Overview
The $lastn query meets the common need for searching for the most recent or last n=number of observations for a subject. For example, retrieving the last 5 temperatures for a patient to view trends or fetching the most recent laboratory results or vitals signs.

Please see more details in the [LastN Operation FHIR specification page](https://build.fhir.org/observation-operation-lastn.html){target="_blank"}

Firely server does implement its own custom vonk.plugin.lastN plugin which is available against the full server however due to the fact that we are developing against the facade we were unable to use this plug in an needed to implement a custom NHS Wales LastN plugin. More details can be found in the developer guide on how the plug in is developed and set up.

### Functionality
The NHS Wales plugin supports querying for LastN Observation Results using the following parameters:

#### Max
max is an optional input parameter to the lastn query operation. It is used to specify the maximum number of Observations to return from each group. For example for the query "Fetch the last 3 results for all vitals for a patient" max = 3. If not supplied max defaults to 1.


- max=int

```
get [host]/Observation/$lastn?max=2&patient=Patient/NN046351-149&code=ACE,CREAT
```

### Test Codes
Observation code is a required parameter, you can search for th etest code in a couple of ways:

- code={comma separated code or System|Code}

#### Code only
This will default to the OBXResultCode
```
get [host]/Observation/$lastn?patient=Patient/NN046351-149&code=ACE
get [host]/Observation/$lastn?patient=Patient/NN046351-149&code=ACE,17OHPDFT

```

#### System|Code
This will check against the correct field accoring to system. In this case the wrrs-test-code is OBXResultCode

```
get [host]/Observation/$lastn?patient=Patient/NN046351-149&code=code=https://fhir.nhs.wales/Id/wrrs-test-code|ACE
get [host]/Observation/$lastn?patient=Patient/NN046351-149&code=https://fhir.nhs.wales/Id/wrrs-test-code|ACE,https://fhir.nhs.wales/Id/wrrs-test-code|17OHPDFT
```

#### Other Coding options

The LastN operation supports search against:

- https://fhir.nhs.wales/Id/wrrs-test-code (eg. ACE)
- https://fhir.nhs.wales/Id/lims-test-code (eg. B3503)
- http://read.info/readv2 (eg. 44CH.)
- http://snomed.info/sct (eg. 999681000000101)

```
get [host]/Observation/$lastn?max=2&patient=Patient/NN046351-149&code=https://fhir.nhs.wales/Id/wrrs-test-code|ACE
get [host]/Observation/$lastn?max=2&patient=Patient/NN046351-149&code=https://fhir.nhs.wales/Id/lims-test-code|B3503
get [host]/Observation/$lastn?max=2&patient=Patient/NN046351-149&code=http://read.info/readv2|44CH.
get [host]/Observation/$lastn?max=2&patient=Patient/NN046351-149&code=http://snomed.info/sct|999681000000101

```

### Patient
There are two options for searching against patient, at least one must be used when using lastn to search:

#### Patient Resource ID
```
get [host]/Observation/$lastn?patient=Patient/NN046351-149&code=ACE
get [host]/Observation/$lastn?patient=Patient/NN046351-149&code=ACE,17OHPDFT

```

#### Patient Identifier

Using patient identifier will support the exact same search functionality as patient search and so many comma separated identifiers can be included.

```
get [host]/Observation/$lastn?subject:Patient.identifier=https://fhir.hduhb.nhs.wales/Id/pas-identifier|NN046351&code=ACE
get [host]/Observation/$lastn?subject:Patient.identifier=https://fhir.hduhb.nhs.wales/Id/pas-identifier|NN046351&code=ACE,17OHPDFT
```

### Category
Not implemented yet, dependent on NHS Wales OBX FHIR standards to include the category and an agreed way to group and search by category.

</div>