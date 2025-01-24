### {{page-title}}
The Provenance resource tracks information about the activity that created, revised, deleted, or signed a version of a resource, describing the entities and agents involved. Whenever patient records or patient record items are created or amended an associated provenance record can also be recorded which details the entities and processes responsible for the update. 

For example:
* When a Patient resource is updated as a result of a HL7 v2 demographics update message, a Provenance resource can be created that references the new version of the Patient resource, together with details of the system responsible for sending the message and the component responsible for processing the update. The Provenance resource may also provide a link to HL7 v2 message that triggered the update. 
* A clinical system record a new Observation resource to a datastore via a FHIR API. An additional Provenance resource can also be recorded by the originating system to indicate that it was responsible for inserting the new Observation record.

Provenance resources can be used in this way to provide information about the context in which the information in a resource was obtained, and to provide traceability in order to fix bugs and maintain data quiality.

The data recorded within a Provenance resource is in addition to other items of reference data recorded as part of a FHIR resource, such as the clinician (Practitioner) responsible for adding new data, or the Encounter during which the data was recorded. This data is generally included within the definition of the FHIR resource e.g. the clinician responsible for an observation is recorded in the Observation.performer field.
