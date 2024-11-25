## {{page-title}}
The Data Standards Wales Provenance FHIR profile binds the Provenance.activity field to the Data Standards Wales Provenance Activity value set. The table below provides additional guidance when seeking to determine the most appropriate value for this field when adding data to the Care Data Repository. 

|Code|Comments|
|----|--------|
|amend|Use when updating an existing record on Care Data Repository|
|originate|Reserved for bulk load/initial load of data into the Care Data Repository from external systems|
|receive|To be used when creating FHIR resources in the Care Data Repository, either via an API call from a client system, or as data is created as a result of messages received within a stream of data, e.g. HL7v2 demographic or ADT message streams|
|merge|Used for merging records e.g. Patient record merges e.g. as result of an HL7v2  ADT^A40 etc.|
|verify|To be used when recording 'Demographics as Recorded' provenance (see below)|
