## {{page-title}}

This page describes the published versions of this implementation guide and differences between versions:

### v2.3.0 STU2
Package: 
* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions,text:Profiles and Extensions}}:
    * New Profiles
        * DataStandardsWales-Composition
        * DataStandardsWales-Condition        
        * DataStandardsWales-Consent
        * DataStandardsWales-DocumentReference
        * DataStandardsWales-Encounter-UEC
        * DataStandardsWales-ImmunizationRecommendation
    * New Extensions
        * DataStandardsWales-AdministeredProduct
        * DataStandardsWales-DateProcedureLastUpdated        
        * DataStandardsWales-DocumentAttribute
        * DataStandardsWales-DocumentDigitalStatus
        * DataStandardsWales-DocumentErrorAction
        * DataStandardsWales-DocumentErrorStatus
        * DataStandardsWales-ForecastCreationSource
        * DataStandardsWales-SourceSystem
        * DataStandardsWales-UECAttendanceCategory
        * DataStandardsWales-UECDischargeInformationGiven
        * DataStandardsWales-UECExpectedTimeOfTreatment
    * New R5 backport Extensions:      
        * DataStandardsWales-DocumentAttester
        * DataStandardsWales-DocumentVersion
        * DataStandardsWales-Immunization.basedOn
    * Changes to Profiles
        * DataStandardsWales-Appointment
            * Updated version from 1.0.0 to 1.0.1
            * .reasonReference. Added reference to DataStandardsWales-ImmunizationRecommendation
        * DataStandardsWales-DiagnosticReport
            * Updated version from 0.1.1 to 0.1.2
            * .basedOn. Added reference to DataStandardsWales-ImmunizationRecommendation
        * DataStandardsWales-DiagnosticReport-Lab
            * Updated version from 0.1.0 to 0.1.1
            * .basedOn. Added reference to DataStandardsWales-ImmunizationRecommendation
        * DataStandardsWales-Encounter
            * Updated version from 1.0.0 to 1.0.1
            * .appointment. Added reference to DataStandardsWales-Appointment
            * .reasonReference. Added reference to DataStandardsWales-ImmunizationRecommendation
            * .serviceProvider. Added Must Support flag.
        * DataStandardsWales-ImagingStudy
            * Updated version from 0.0.6 to 0.0.7
            * .basedOn. Added reference to DataStandardsWales-Appointment
        * DataStandardsWales-Immunization
            * Updated version from 0.1.1 to 1.0.0
            * Updated status from draft to active
            * Removed experimental flag
            * New extensions added:
                * DataStandardsWales-AdministeredProduct
                * DataStandardsWales-DateProcedureLastUpdated
                * DataStandardsWales-ForecastCreationSource
                * DataStandardsWales-Immunization.basedOn
            * R5 backport extension:
                * DataStandardsWales-Immunization.basedOn
            * Terminology binding changes:
                * .protocolApplied.targetDisease. ValueSet reverted to UK Core STU2 so changed from covid-19-diseases to immunization-target-disease
            * Binding strength changes:
                * .protocolApplied.targetDisease. From required to example
            * .basedOn. Added reference to DataStandardsWales-ImmunizationRecommendation
        * DataStandardsWales-MedicationRequest
            * Updated version from 1.1.1 to 1.1.2
            * .basedOn. Added reference to DataStandardsWales-ImmunizationRecommendation
        * DataStandardsWales-Observation
            * Updated version from 0.1.1 to 0.1.2
            * .basedOn. Added reference to DataStandardsWales-ImmunizationRecommendation
            * .reasonReference. Added reference to DataStandardsWales-ImmunizationRecommendation
        * DataStandardsWales-MedicationRequest
            * Updated version from 1.1.1 to 1.1.2
            * .basedOn. Added reference to DataStandardsWales-ImmunizationRecommendation
        * DataStandardsWales-Observation
            * Updated version from 0.1.1 to 0.1.2
            * .basedOn. Added reference to DataStandardsWales-ImmunizationRecommendation 
        * DataStandardsWales-Practitioner
            * Updated version from 1.1.2 to 1.1.3
            * Cardinality changes:
                * identifier:nadexIdentifier. From 0..1 to 0..* 
        * DataStandardsWales-Practitioner
            * Updated version from 1.1.1 to 1.1.2
            * .specialty. Changed valueset binding from required to extensible to align with UK Core
* {{pagelink:Home/FHIR-Assets/Terminology,text:Terminology}}:
    * New Value Sets 
        * Data Standards Wales Document Category
        * Data Standards Wales Document Digital Status
        * Data Standards Wales Document Type
        * Data Standards Wales Encounter Type 
        * Data Standards Wales UEC Activity Type
        * Data Standards Wales UEC Acuity
        * Data Standards Wales UEC Arrival Mode
        * Data Standards Wales UEC Attendance Category
        * Data Standards Wales UEC Attendance Source
        * Data Standards Wales UEC Care Consultation Mechanism
        * Data Standards Wales UEC Discharge Destination
        * FHIR Standards Wales Document Attribute
        * FHIR Standards Wales Document Error Action
        * FHIR Standards Wales Document Error Status
        * PAS Event Type
    * New Code Systems
        * Data Standards Wales Document Category
        * Data Standards Wales Document Digital Status
        * Data Standards Wales UEC Activity Type
        * Data Standards Wales UEC Attendance Category
        * Data Standards Wales UEC Care Consultation Mechanism
        * FHIR Standards Wales Document Attribute
        * FHIR Standards Wales Document Error Action
        * FHIR Standards Wales Document Error Status
        * WPAS Event Type
* {{pagelink:Home/FHIR-Assets/Naming-Systems.page.md,text:Naming Systems}}
    * Changes to Naming Systems
        * Namespaces for PAS Appointment ids
            * Updated value from pas-event-code to pas-event-identifier
            * Changed name from AppointmentIdentifier to XXXXPASAppointmentIdentifier where XXXX is the healthboard/trust abbreviation
        * New Naming Systems
            * Namespaces for PAS Practitioner id. This is to aid in the mapping of the HL7 v2 messages into FHIR. It is to the capture 'local' identifiers for practitioners where they may not exist in the CDR.
            * Namespaces for LIMS TCLE and TCL system identifiers. This is to aid in the mapping of the HL7 v2 messages into FHIR. It is to the capture 'local' identifiers for LIMS where they may not exist in the CDR. These include LIMS identifiers for procedure, report and specimen type codes.
            * Namespaces for PAS upi identifiers. These additional identifiers are for referrals and appointments and encounters so CDR can identify when an appointment has come from a referral and when a patient has e.g arrived at their appointment.  CDR would store this value as an additional identifier against each referral, appointment and encounter in the existing identifier FHIR array.
            * Namespace for WCRS DocumentId values
            * Namespace for WCRS DocumentSupersessionSetId values
        * Namespaces for SubSpeciality ids
            * Removed all SubSpeciality Namespaces
* {{pagelink:Home/Example-Index.page.md,text:Examples}}:
    * New Examples
        * Document Reference
            * {{pagelink:Example-DataStandardsWales-DocumentReference-EncounterBased, text:Encounter-based}}
            * {{pagelink:Example-DataStandardsWales-DocumentReference-EventBased, text: Event-based}}
            * {{pagelink:Example-DataStandardsWales-DocumentReference-NotEventBased, text: Not event-based}}
            * {{pagelink:Example-DataStandardsWales-DocumentReference-MisfiledNotEventBased, text: Misfiled (document not event-based)}}

Guide:
* General improvements to IG that include fixing spelling mistakes and correcting grammatical errors
* Added a new page to outline the DataStandardsWales-Consent profile
* Added a new page to outline the DataStandardsWales-Condition profile
* Added a new page to outline the DataStandardsWales-Composition profile
* Added a new page to outline the DataStandardsWales-Encounter-UEC profile
* Added a new page to outline the DataStandardsWales-ImmunizationRecommendation profile
* Added a new page to outline the DataStandardsWales-DocumentReference profile
* Added new pages to outline the Data Standards Wales Extensions created in this release
* Added new pages to outline the Data Standards Wales Value Sets created in this release
* Added new pages to outline the Data Standards Wales Code Systems created in this release
* Added new pages to outline the Data Standards Wales Examples created in this release
* Removed DataStandardsWales-Dosage profile from main index
* Removed NHS Wales Identity Provider User ID (also known as Nadex) section from Naming Systems page
* Added Health Board PAS names to AppointmentIdentifier Name in Naming Systems table
* Updated Provenance Guidance page
* Moved DataStandardsWales-Device from Diagnostics to Entities in Resource Index page
* Added HL7 International R4 tile to Related Pages
* Added HL7 International R5 tile to Related Pages
+ Added namespaces for WCRS DocumentId and WCRS DocumentSupersessionSetId values in Naming Systems table

### v2.2.0 STU2
Package: 
* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions,text:Profiles and Extensions}}:
    * New Profiles
        * DataStandardsWales-Appointment        
    * Changes to Profiles
        * DataStandardsWales-Encounter
            * Updated version from 0.1.1 to 1.0.0
            * Updated status from draft to active
            * Added .extension:Speciality 
        * DataStandardsWales-Practitioner
            * Updated nadexIdentifier slice to include a fixed system url
        * DataStandardsWales-ServiceRequest
            * Updated version from 0.1.1 to 1.0.0
            * Updated status from draft to active
            * .code. Reverted minimum cardinality from 1..1 to 0..1 in line with UK Core
            * .performer. Added Must Support flag
        * DataStandardsWales-Observation-VitalSigns
            * Updated version from 1.0.0 to 1.1.0
            * Status fixed value removed
        * DataStandardsWales-Observation-VitalSigns-BMI
            * Updated version from 1.0.0 to 1.1.0
            * Status fixed value removed
        * DataStandardsWales-Observation-VitalSigns-BodyHeight
            * Updated version from 1.0.0 to 1.1.0
            * Status fixed value removed
        * DataStandardsWales-Observation-VitalSigns-BodyWeight
            * Updated version from 1.0.0 to 1.1.0
            * Status fixed value removed
    * New Extensions
        * DataStandardsWales-Speciality 
* {{pagelink:Home/FHIR-Assets/Naming-Systems.page.md,text:Naming Systems}}
    * New Naming Systems
        * Namespaces for PAS Appointment ids
        * Namespaces for PAS Sub-speciality codes
* {{pagelink:Home/Example-Index.page.md,text:Examples}}:
    * New Examples
        * Observation Vital Signs 
            * {{pagelink:Example-DataStandardsWales-Observation-VitalSigns-BMI,text: BMI}}
            * {{pagelink:Example-DataStandardsWales-Observation-VitalSigns-HeadCircumference,text: Head Circumference}}
            * {{pagelink:Example-DataStandardsWales-Observation-VitalSigns-MaternalHeight,text: Maternal Height}}
            * {{pagelink:Example-DataStandardsWales-Observation-VitalSigns-Weight,text: Weight}}
        * Provenance
            * {{pagelink:Example-DataStandardsWales-Provenance-DemographicUpdate, text:Example Provenance record linked to a Patient demographic update as result of an HL7v2 patient demographic update }}
            * {{pagelink:Example-DataStandardsWales-Provenance-MultipleTargets, text:Example Provenance record with multiple targets e.g. for growth chart observations}}
            * {{pagelink:Example-DataStandardsWales-Provenance-DemographicsAsRecorded, text:Example Provenance record showing the DemographicsAsRecorded extension}}
        * Questionnaire
            * {{pagelink:Example-DataStandardsWales-Questionnaire-GrowthChartCondition,text: Growth Chart Condition}}
        * Questionnaire Response
            * {{pagelink:Example-DataStandardsWales-QuestionnaireResponse-GrowthChartCondition,text: Growth Chart Condition Response}}
    * Removed Examples
        * Provenance
            * Example Provenance - Amend Device and Document Reference
            * Example Provenance - Amend where Device is unavailable
            * Example Provenance - Growth Charts 
Guide: 
* Added a new page to outline the DataStandardsWales-Appointment profile
* Updates to the DataStandardsWales-Provenance profile page, along with updated examples
* Added a new page to outline the DataStandardsWales-Speciality extension
* Updated relevant pages within the Guide to reflect changes outlined in Package
* Created a new section for {{pagelink:Home/Guidance/Growth-Charts,text: Growth Charts}} guidance

### v2.1.0 STU2
Package:
* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions,text:Profiles and Extensions}}:
    * New Profiles
        * DataStandardsWales-Observation-VitalSigns
        * DataStandardsWales-Observation-VitalSigns-BMI
        * DataStandardsWales-Observation-VitalSigns-BodyWeight
        * DataStandardsWales-Observation-VitalSigns-BodyHeight
        * DataStandardsWales-Questionnaire
        * DataStandardsWales-QuestionnaireResponse
        * DataStandardsWales-RelatedPerson
    * Changes to Profiles
        * DataStandardsWales-AllergyIntolerance
            * Updated version from 0.1.0 to 0.1.1
            * .recorder. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
            * .asserter. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
            * .note.author. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
            * .reaction.note.author. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
        * DataStandardsWales-AllergyList
            * Updated version from 1.2.0 to 1.2.1
            * .note.author. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
        * DataStandardsWales-Device
            * Updated version from 0.0.1 to 0.0.2
            * note.author
                * Removed reference to HL7 Practitioner. Added reference to DataStandardsWales-Practitioner
                * Removed reference to HL7 Patient. Added reference to DataStandardsWales-Patient
                * Removed reference to HL7 RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
                * Removed reference to HL7 Organization. Added reference to DataStandardsWales-Organization
        * DataStandardsWales-DiagnosticReport
            * Updated version from 0.1.0 to 0.1.1
            * .basedOn. Removed reference to UKCore-ServiceRequest. Added reference to DataStandardsWales-ServiceRequest
        * DataStandardsWales-Encounter
            * Updated version from 0.1.0 to 0.1.1
            * .basedOn. Removed reference to HL7 ServiceRequest. Added reference to DataStandardsWales-ServiceRequest
            * .participant.individual. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
        * DataStandardsWales-Immunization
            * Updated version from 0.1.0 to 0.1.1
            * .note.author. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
        * DataStandardsWales-ImagingStudy
            * Updated version from 0.0.5 to 0.0.6
            * note.author
                * Removed reference to HL7 Practitioner. Added reference to DataStandardsWales-Practitioner
                * Removed reference to HL7 Patient. Added reference to DataStandardsWales-Patient
                * Removed reference to HL7 RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
                * Removed reference to HL7 Organization. Added reference to DataStandardsWales-Organization
        * DataStandardsWales-MedicationAdministration
            * Updated version from 1.1.0 to 1.1.1
            * .note.author. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
            * .performer.actor. 
                * Removed reference to UKCore-Device. Added reference to DataStandardsWales-Device
                * Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
        * DataStandardsWales-MedicationDispense
            * Updated version from 1.1.0 to 1.1.1
            * .performer.actor. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
            * .note.author. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson 
        * DataStandardsWales-MedicationList
            * Updated version from 1.1.0 to 1.1.1
            * .note.author. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson 
        * DataStandardsWales-MedicationRequest
            * Updated version from 1.1.0 to 1.1.1
            * .reported. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
            * .encounter. Removed reference to HL7 Encounter. Added reference to DataStandardsWales-Encounter
            * .requester. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
            * .performer. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
        * DataStandardsWales-MedicationStatement
            * Updated version from 1.1.0 to 1.1.1
            * .informationSource. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
            * note.author. 
                * Removed reference to HL7 RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
                * Removed reference to HL7 Practitioner. Added reference to DataStandardsWales-Practitioner
                * Removed reference to HL7 Patient. Added reference to DataStandardsWales-Patient
                * Removed reference to HL7 Organization. Added reference to DataStandardsWales-Organization
        * DataStandardsWales-Patient
            * Updated version from 1.2.0 to 1.2.1
            * .link.other
                * Removed reference to HL7 Patient. Added reference to DataStandardsWales-Patient
                * Removed reference to HL7 RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
        *  DataStandardsWales-Observation-Lab
            * Updated version from 0.1.0 to 0.1.1
            * .performer
                * Removed reference to HL7 Practitioner. Added reference to DataStandardsWales-Practitioner
                * Removed reference to HL7 Patient. Added reference to DataStandardsWales-Patient
                * Removed reference to HL7 Organization. Added reference to DataStandardsWales-Organization
                * Removed reference to HL7 RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
                * Removed reference to HL7 PractitionerRole. Added reference to DataStandardsWales-PractitionerRole
            * .note.author. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
        * DataStandardsWales-Observation
            * Updated version from 0.1.0 to 0.1.1
            * .performer. Removed reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
            * .note.author. Removed  reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
        * DataStandardsWales-Organization
            * Updated version from 1.1.0 to 1.1.1
            * .endpoint. Removed reference to HL7 Endpoint. Added reference to DataStandardsWales-Endpoint
        * DataStandardsWales-Practitioner
            * Updated version from 1.1.1 to 1.1.2
            * Added slice named NADEX-Identifier
        * DataStandardsWales-Provenance
            * Updated version from 0.0.1 to 0.0.2
            * .agent.who. Removed reference to HL7 RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
            * .agent.
                * Removed reference to HL7 Practitioner. Added reference to DataStandardsWales-Practitioner
                * Removed reference to HL7 PractitionerRole. Added reference to DataStandardsWales-PractitionerRole
                * Removed reference to HL7 RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
                * Removed reference to HL7 Patient. Added reference to DataStandardsWales-Patient
                * Removed reference to HL7 Device. Added reference to DataStandardsWales-Device
                * Removed reference to HL7 Organization. Added reference to DataStandardsWales-Organization
            * agent.onBehalfOf
                * Removed reference to HL7 Practitioner. Added reference to DataStandardsWales-Practitioner
                * Removed reference to HL7 PractitionerRole. Added reference to DataStandardsWales-PractitionerRole
                * Removed reference to HL7 RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
                * Removed reference to HL7 Patient. Added reference to DataStandardsWales-Patient
                * Removed reference to HL7 Device. Added reference to DataStandardsWales-Device
                * Removed reference to HL7 Organization. Added reference to DataStandardsWales-Organization
            * .signature.who.
                * Removed reference to HL7 Practitioner. Added reference to DataStandardsWales-Practitioner
                * Removed reference to HL7 PractitionerRole. Added reference to DataStandardsWales-PractitionerRole
                * Removed reference to HL7 RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
                * Removed reference to HL7 Patient. Added reference to DataStandardsWales-Patient
                * Removed reference to HL7 Device. Added reference to DataStandardsWales-Device
                * Removed reference to HL7 Organization. Added reference to DataStandardsWales-Organization
            * .signature.onBehalfOf.
                * Removed reference to HL7 Practitioner. Added reference to DataStandardsWales-Practitioner
                * Removed reference to HL7 PractitionerRole. Added reference to DataStandardsWales-PractitionerRole
                * Removed reference to HL7 RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
                * Removed reference to HL7 Patient. Added reference to DataStandardsWales-Patient
                * Removed reference to HL7 Device. Added reference to DataStandardsWales-Device
                * Removed reference to HL7 Organization. Added reference to DataStandardsWales-Organization
		* DataStandardsWales-ServiceRequest
            * Updated version from 0.1.0 to 0.1.1
            * .requester. Removed  reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
            * .performer. Removed  reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
            * .note.author. Removed  reference to UKCore-RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
        * DataStandardsWales-Specimen
            * Updated version from 0.1.0 to 0.1.1
            * .note.author
                * Removed reference to HL7 Practitioner. Added reference to DataStandardsWales-Practitioner
                * Removed reference to HL7 Patient. Added reference to DataStandardsWales-Patient
                * Removed reference to HL7 Organization. Added reference to DataStandardsWales-Organization
                * Removed reference to HL7 RelatedPerson. Added reference to DataStandardsWales-RelatedPerson
    * New Extensions
        * DataStandardsWales-RecordingSetting
* {{pagelink:Home/FHIR-Assets/Terminology,text:Terminology}}:
    * New Value Sets
        * DataStandardsWales-BloodPressure
        * DataStandardsWales-BloodPressureDiastolic
        * DataStandardsWales-BloodPressureSystolic
        * DataStandardsWales-BMI
        * DataStandardsWales-BodyHeightMeasurement
        * DataStandardsWales-BodyPosition
        * DataStandardsWales-BodyTemperature
        * DataStandardsWales-BodyWeightMeasurement
        * DataStandardsWales-HeadCircumferenceMeasurement
        * DataStandardsWales-HeartRate
        * DataStandardsWales-ObservationVitalSignsType
        * DataStandardsWales-OxygenSaturation
        * DataStandardsWales-QuestionnaireQuestionCodes
        * DataStandardsWales-RecordingSetting
        * DataStandardsWales-RespirationRate
    * New Code Systems
        * DataStandardsWales-RecordingSetting
* {{pagelink:Home/FHIR-Assets/Naming-Systems.page.md,text:Naming Systems}}
    * New Naming Systems
        * NADEX-Identifier
* {{pagelink:Home/Example-Index.page.md,text:Examples}}:
    * New Examples
        * Provenance
            * {{pagelink:Example-DataStandardsWales-Provenance-Growth-Charts, text: Growth Chart}} 

Guide:
* Updated relevant pages within the Guide to reflect changes outlined in Package.
* General improvements including removing of duplicate sections, spelling mistakes and capitalisation of abbreviations (i.e. DM+D)

### v2.0.0 STU2
As part of our commitment to quality assurance and interoperability, we undertook an exercise to review and align the existing FHIR Standards Wales Package with UK Core STU2 (fhir.r4.ukcore.stu2 2.0.1). This resulted in us rationalising the FHIR Standards Wales Package where possible, removing detail that can already be derived from UK Core STU2, whilst still adhering to the principles of FHIR and supporting Wales specific content where required. 
In addition to the removal of replicate content, the following changes were made: 

Package:
* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions,text:Profiles and Extensions}}:
    * Changes to Profiles
        * DataStandardsWales-AllergyIntolerance
            * Updated version number from 1.0.0 to 1.1.0
            * Reference changes:
                * .encounter. Removed reference to UKCore-Encounter. Added reference to DataStandardsWales-Encounter
                * extension:evidence. Removed reference to UKCore-DiagnosticReport. Added reference to DataStandardsWales-DiagnosticReport
            * Binding strength changes:
                * .reaction.substance. From extensible to preferred
	            * .reaction.manifestation. From extensible to preferred
	            * .reaction.exposureRoute. From extensible to preferred
        * DataStandardsWales-AllergyList
            * Updated version number from 1.1.0 to 1.2.0
            * Reference changes:
                * .encounter. Removed reference to UKCore-Encounter. Added reference to DataStandardsWales-Encounter
                * .source. Removed reference to Device. Added reference to DataStandardsWales-Device
        * DataStandardsWales-DiagnosticReport
            * Updated version number from 0.0.5 to 0.1.0
            * Reference changes:
                * .performer. Added reference to CareTeam
            * Removed Slices:
                * .code
                * .conclusionCode
        * DataStandardsWales-DiagnosticReport-Lab
            * Updated version number from 0.0.5 to 0.1.0
            * .conclusionCode.Removed Slice
            * Reference changes:
                *  .basedOn. Removed reference to HL7 ServiceRequest. Added reference to UKCore-ServiceRequest
        * DataStandardsWales-Dosage   
            * Updated version number from 0.0.5 to 0.1.0
            * All Must Support flags removed 
            * Binding strength changes:
                * .asNeeded[]. From example to preferred
            * Binding terminology changes:
                * .site. Removed binding to value set SNOMEDCTAnatomicalStructureForAdministrationSiteCodes. Added binding to value set UKCoreBodySite. Binding strength set as preferred
                * .route. Removed binding to value set SNOMEDCTAdministrationMethodCodes. Added binding to value set UKCoreSubstanceOrProductAdministrationRoute. Binding strength set as preferred
                * .method. Removed binding to value set SNOMEDCTAdministrationMethodCodes. Added binding to value set UKCoreUKCoreMedicationDosageMethod. Binding strength set as preferred 
         * DataStandardsWales-Encounter
            * Updated version number from 0.0.5 to 0.1.0
            * Must Support changes:
                * .reasonCode. Added must support
	            * .reasonReference. Added must support
	        * Extension changes:
	            * .hospitalization. Added .extension:admissionMethod 
            * Reference changes:
                * .reasonReference. Removed reference to UKCore-Observation. Added reference to DataStandardsWales-Observation.
                * .reasonReference. Removed reference to HL7 Condition. Added reference to UKCore-Condition.
                *.reasonReference. Removed reference to HL7 Procedure. Added reference to UKCore-Procedure.
        * DataStandardsWales-ImagingStudy
            * Reference changes:
                * .reasonReference. Removed HL7 Condition. Added reference to UKCore-Condition
        * DataStandardsWales-Immunization
            * Updated version number from 0.0.5 to 0.1.0
            * Binding strength changes:
	            *.statusReason. From example to preferred
	        * Binding terminology changes:
	            * .vaccineCode. Added binding to value set UKCore-VaccineCode. Binding strength set as preferred
	            * .site. Removed binding to value set UKCore-BodySite. Added binding to value set UKCore-ImmunizationAdministrationBodySite. Binding strength set as preferred
	            * .route. Added binding to value set UKCore-SubstanceOrProductAdministrationRoute. Binding strength set as preferred
            * Reference changes:
                * .protocolApplied.authority . Removed reference to UKCore-Organization. Added reference to DataStandardsWales-Organization
        * DataStandardsWales-Location
            * Updated version number from 1.0.1 to 1.1.0
        * DataStandardsWales-Medication
            * Updated version number from 1.0.0 to 1.1.0
            * Reference changes:
                * .manufacturer. Added reference to DataStandardsWales-Organization
                * .ingredient.item[]. Removed reference to Medication. Added reference to DataStandardsWales-Medication
        * DataStandardsWales-MedicationAdministration
            * Updated version number from 1.0.1 to 1.1.0
            * Reference changes:
                * .reasonReference. Removed references to UKCore-Observation and UKCore-DiagnosticReport. Added references to DataStandardsWales-Observation and DataStandardsWales-DiagnosticReport
                * .performer.actor. Removed reference to UKCore-Device. Added reference to DataStandardsWales-Device
            * Binding strength changes:
                * .dosage.site. From extensible to preferred
                * .dosage.route. From extensible to preferred
                * .dosage.method. From extensible to preferred
        * DataStandardsWales-MedicationDispense
            * Updated version number from 1.0.1 to 1.1.0
            * Must Support changes:
                * .dosageInstruction.text. Added must support
                * .dosageInstruction.timing. Added must support
                * .dosageInstruction.doseAndRate. Added must support
                * .dosageInstruction.doseAndRate.dose[]. Added must support
                * .dosageInstruction.doseAndRate.rate[]. Added must support
            * Binding strength changes:
                * .dosageInstruction.site. From extensible to preferred
                * .dosageInstruction.route. From extensible to preferred
                * .dosageInstruction.method. From extensible to preferred
            * Binding terminology changes:
                * .dosageInstruction.asNeeded[]. Removed binding to value set UKCoreMedicationPrecondition. Added binding to value set SNOMEDCTMedicationAsNeededReasonCodes. Binding strength set as preferred     
            * Reference changes:
                * .context. Removed reference to UKCore-Encounter. Added reference for DataStandardsWales-Encounter
                * .performer.actor. Removed reference to UKCore-Device. Added reference for DataStandardsWales-Device
            * Cardinality change:
                * .receiver. Cardinality changed from 0:1 to 0:* by UK Core STU2
        * DataStandardsWales-MedicationList
            * Updated version number from 1.0.0 to 1.1.0
            * .source. Removed reference to UKCore-Device.Added reference for DataStandardsWales-Device
        * DataStandardsWales-MedicationRequest 
            * Updated version number from 1.0.0 to 1.1.0  
            * Must Support changes:
                * .dosageInstruction. Added must support
                * .dosageInstruction.text. Added must support
                * .dosageInstruction.timing. Added must support
                * .dosageInstruction.doseAndRate. Added must support
                * .dosageInstruction.doseAndRate.dose[]. Added must support
                * .dosageInstruction.doseAndRate.rate[]. Added must support
            * Binding strength changes:
                * .dosageInstruction.site. From extensible to preferred
                * .dosageInstruction.route. From extensible to preferred
                * .dosageInstruction.method. From extensible to preferred
            * Binding terminology changes:
                * .dosageInstruction.asNeeded[]. Removed binding to value set UKCoreMedicationPrecondition. Added binding to value set SNOMEDCTMedicationAsNeededReasonCodes. Binding strength set as preferred     
            * Reference changes:
                * .requester. Removed reference to Device. Added reference to DataStandardsWales-Device
                * .reasonReference. Removed Reference to UK Core Observation. Added Reference to DataStandardsWales-Observation
        * DataStandardsWales-MedicationStatement
            * Updated version number from 1.0.0 to 1.1.0
            * Must Support changes:
                * .dosage. Added must support
            * Binding strength changes:
                * .dosage.site. From extensible to preferred
                * .dosage.route. From extensible to preferred
                * .dosage.method. From extensible to preferred
            * Binding terminology changes:
                * .dosage.asNeeded[]. Removed binding to value set UKCoreMedicationPrecondition. Added binding to value set SNOMEDCTMedicationAsNeededReasonCodesSet. Binding strength set as preferred
            * Reference changes:
                * .basedOn. Removed reference to UKCore-ServiceRequest. Added reference to DataStandardsWales-ServiceRequest
                * .reasonReference. Removed reference to HL7 Condition. Added reference to UKCore-Condition
        * DataStandardsWales-Observation
            * Updated version number from 0.0.6 to 0.1.0
            * Reference changes:
                * .basedOn. Removed reference to MedicationRequest. Added reference to DataStandardsWales-MedicationRequest
                * .partOf. Removed references to MedicationAdministration, MedicationDispense, MedicationStatement, Procedure and Immunization. Added references to DataStandardsWales-MedicationAdministration, DataStandardsWales-MedicationDispense, DataStandardsWales-MedicationStatement, DataStandardsWales-Immunization, and UKCore-Procedure
                * .subject. Removed reference to Device. Added reference to DataStandardsWales-Device
                * .note.author[]. Added references to UKCore-RelatedPerson, DataStandardsWales-Organization, DataStandardsWales-Patient, and DataStandardsWales-Practitioner
                * .device. Removed reference to Device. Added reference to DataStandardsWales-Device
                * .hasMember. Added references to QuestionnaireResponse and MolecularSequence
            * Slices removed:
                * .code.coding
                * .coding:snomedCT
                * .coding:loinc
                * .bodySite.coding
                * .bodySite.coding:snomedCT
        * DataStandardsWales-Observation-Lab
            * Updated version from 0.0.5 to 0.1.0
            * Reference changes:
                * .subject. Removed references to Group, Device and DataStandardWales-Location
                * .device. Removed reference to Device. Added reference to DataStandardWales-Device
                * .hasMember. Added references to QuestionnaireResponse and MolecularSequence
            * Binding terminology changes:
                * .code. Removed binding to value set LOINCCodes. Added binding to value set UKCore-PathologyAndLaboratoryMedicineObservables. Binding strength set as preferred
            * Slices removed:
                * .code.coding
                * .code.coding:snomedCT
                * .code.coding:loinc
                * .bodySite.coding
                * .bodySite.coding:snomedCT
                * .component.code.coding 
                * .component.code.coding:snomedCT
        * DataStandardsWales-Organization
            * Updated version from 1.0.0 to 1.1.0
        * DataStandardsWales-Patient
            * Updated version from 1.1.0 to 1.2.0
            * Slicing changes:
                * .identifier:bcuhbCentralPasIdentifier renamed to  .identifier:bcuhbPasIdentifier. Fixed Value, Short Description and Definition updated to correspond.
            * Slices removed:
                * .identifier. Removed slices for bcuhbEastPasIdentifier and bcuhbWestPasIdentifier
        * DataStandardsWales-Practitioner
            * Updated version number from 1.0.1 to 1.1.1 
            * Must Support changes:
                * .identifier.system. Added must support
                * .identifier.value. Added must support
                * .identifier:gdcNumber.system. Added must support
                * .identifier:gdcNumber.value. Added must support
                * .identifier:gmcNumber.system. Added must support
                * .identifier:gmcNumber.value. Added must support
                * .identifier:gmpNumber.system. Added must support
                * .identifier:gmpNumber.value. Added must support
                * .identifier:hcpcNumber.system. Added must support
                * .identifier:hcpcNumber.value. Added must support
                * .identifier:nmcNumber.system. Added must support
                * .identifier:nmcNumber.value. Added must support
                * .identifier:gphcCode.system. Added must support
                * .identifier:gphcCode.value. Added must support
                * .identifier:sdsUserId.system. Added must support
                * .identifier:sdsUserId.value. Added must support
                * .name.family. Added must support
                * .telecom. Added must support
                * .telecom.system. Added must support
                * .telecom.value. Added must support
        * DataStandardsWales-PractitionerRole
            * Updated version from 1.0.0 to 1.1.0
            * Must Support changes:
                * .location. Added must support
                * .telecom.system. Added must support
                * .telecom.value. Added must support
        * DataStandardsWales-ServiceRequest
            * Updated version number from 0.0.5 to 0.1.0
            * Reference changes:
                * .note.author[]. Removed references to Organization, Patient, Practitioner, and RelatedPerson. Added references to DataStandardsWales-Organization, DataStandardsWales-Patient, DataStandardsWales-Practitioner, and UKCore-RelatedPerson
                * .relevantHistory. Removed reference to Provenance. Added reference to DataStandardsWales-Provenance
            * Binding terminology changes:
                * .orderDetail. Removed ValueSet ServiceRequestOrderDetailsCodes. Replaced with ValueSet UKCoreProcedureCode. Binding changed to preferred
        * DataStandardsWales-Specimen
            * Updated version from 0.0.5 to 0.1.0
            * Binding terminology changes:
                * .type. Removed binding to value set v2.0487. Added binding to value set https://fhir.hl7.org.uk/ValueSet/UKCore-SpecimenType
                * .condition. Removed binding to value set v2.0493. Added binding to value set UKCore-BiopsyState
            * Slices removed:
                * .type.coding
                * .type.coding:snomedCT
                * .collection.bodySite.coding 
                * .collection.bodySite.coding:snomedCT
            * Reference changes:
                * .subject. Removed reference to Device. Added reference to DataStandardsWales-Device
            * Extension changes:
                * Added extension for sampleCategory
                * .collection. Added extension for specialHandling 
                * .collection.collector. Added extension for collectionCollectorR5
                * .collection.bodySite. Added extension for bodySiteReference

Examples:
* Removed Dosage Examples
* Fixed render issues in Immunizations:
    * {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Profiles/Examples/Immunization/Example-DataStandardsWales-Immunization-FluVaccine.page.md,text:Flu Vaccine}}  
    * {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Profiles/Examples/Immunization/Example-DataStandardsWales-Immunization-NotGiven.page.md,text:Not Given}}    
    * {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Profiles/Examples/Immunization/Example-DataStandardsWales-Immunization-ParentPresent.page.md,text:Parent Present}}  
        
Guide:
* Created a new section for {{pagelink:Home/Guidance/provenance}} guidance

                
### v1.2.1 STU1
Package:
* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions,text:Extensions}}:
    * Changes to Profiles    
        * DataStandardsWales-AllergiesList
            * Added Extensions for:
                * DataStandardsWales-SingleRecord-AllergiesListUpdated
                * DataStandardsWales-SingleRecord-AllergiesListConfirmedDateurceTimestamp
                * DataStandardsWales-SingleRecord-AllergiesListConfirmedBy
    * New Extensions
        * DataStandardsWales-SingleRecord-AllergiesListUpdated
        * DataStandardsWales-SingleRecord-AllergiesListConfirmedDateurceTimestamp
        * DataStandardsWales-SingleRecord-AllergiesListConfirmedBy
    * Changes to Extensions
        * DataStandardsWales-CDRPatientRecordType
            * Removed this extension as the data item will be captured in tags
        * DataStandardsWales-CDRSourceTimestamp
            * Removed this extension as the data item will be captured in tags
* {{pagelink:Home/FHIR-Assets/Naming-Systems.page.md,text:Naming Systems}}
    * Changes to Identifiers
        * Consolidated BCUHBCentralPASIdentifier, BCUHBEastPASIdentifier and BCUHBWestPASIdentifier to BCUHBPASIdentifier
* {{pagelink:Home/Example-Index.page.md,text:Examples}}:
    * New examples
        * Immunization
            * {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Profiles/Examples/Immunization/Example-DataStandardsWales-Immunization-FluVaccine.page.md,text:Flu Vaccine}}  
            * {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Profiles/Examples/Immunization/Example-DataStandardsWales-Immunization-NotGiven.page.md,text:Not Given}}    
            * {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Profiles/Examples/Immunization/Example-DataStandardsWales-Immunization-ParentPresent.page.md,text:Parent Present}}  
        * Dosage
            * Drops
            * Inhaler
            * Oral Solution PRN                 
        
Guide:
* Added sections for FHIR Development Initiatives and Communities and FHIR Chat to {{pagelink:Home/Help-and-Support/Related-Pages.page.md,text:Related Pages}}
* Added a section for Change Requests to {{pagelink:Home/Help-and-Support/Help-and-Support.page.md,text:Help and Support}}.
* Created a new {{pagelink:Home/Design/Design-Patterns.page.md,text:Design Patterns}} page.
* Created a new {{pagelink:Home/Help-and-Support/Regular-Meetings.page.md,text:Regular Meetings}} page.
* Created a new {{pagelink:Home/Help-and-Support/Training.page.md,text:Training}} page.



### v1.1.1 STU1
Package:
* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions,text:Profiles}}:
    * Changes to Profiles
        * DataStandardsWales-Provenance   
            * Updated references to use Data Standards Wales profiles     
* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions,text:Extensions}}:
    * Changes to Extensions
        * DataStandardsWales-DemographicsAsRecorded
            * Renamed the DOB extension to birtDate 
            * Updated the extension URL
            * Updated the items within the extension URLs
        * DataStandardsWales-CDRPatientRecordType
            * Updated the name of the extension
        * DataStandardsWales-CDRSourceTimestamp
            * Updated the name of the extension

Guide:
* Updated the contact email address on the {{pagelink:Home/Help-and-Support/Related-Pages.page.md,text:Help and Support-Related Pages}}


            
### v1.1.0 STU1

Package: 
* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions,text:Profiles}}:
    * New Profiles
        * DataStandardsWales-Device
        * DataStandardsWales-Provenance        
    * Changes to Profiles    
        * DataStandardsWales-Patient
            * Added Extensions for:
                * DataStandardsWales-CDRPatientRecordType
                * DataStandardsWales-CDRSourceTimestamp
* {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions,text:Extensions}}:
    * New Extensions
        * DataStandardsWales-CDRPatientRecordType
        * DataStandardsWales-CDRSourceTimestamp
        * DataStandardsWales-DemographicsAsRecorded

* {{pagelink:Home/FHIR-Assets/Terminology,text:Value Sets}}:
    * New Value Sets
        * DataStandardsWales-ProvenanceActivity
        * DataStandardsWales-PatientRecordType

 * {{pagelink:Home/FHIR-Assets/Naming-Systems.page.md,text:Naming Systems}}:
    * Corrected oid references. Changed from 2.16.840.1.113883.2.1.8.1.5.nnn to 2.16.840.1.113883.2.1.8.1.3.nnn    

Guide:
* Updated relevant pages within the Guide to reflect changes outlined in Package.
* Updated {{pagelink:Home/Help-and-Support/Glossary.page.md,text:Glossary}}.
  
* Added definitions for Active, Draft and Experimental to {{pagelink:Home/Introduction/Profile-Descriptions,text:Introduction-Profile Descriptions}}
* Added a link for FHIR PSOM Wales Project Page to {{pagelink:Home/Help-and-Support/Related-Pages.page.md,text:Help and Support-Related Pages}}
* Updated [Wales FHIR Implementation Guide Version History](https://simplifier.net/guide/Wales-FHIR-Implementation-Guide-Version-History-v1.1.0/Home/Version-History.page.md?version=1.1.0) to include links to respective Release Notes.


### v1.0.1 STU1

Package: 
* Profiles:
    * DataStandardsWales-Practitioner
        * Quotes removed from sdsuserid
    * DataStandardsWales-Location
        * Cardinality changed from 1..1 to 0..1:
            * .address
            * .managingOrganization.identifier
    * DataStandardsWales-MedicationDispense
        * Cardinality changed from 1..1 to 0..1:
            * .authorizingPrescription
            * .authorizingPrescription.reference
            * .identifier
            * .performer
            * .location.display
            * .quantity.value
            * .quantity.unit
            * .quantity.system
            * .quantity.code
        * Must support added to:
            * .location
            * .receiver
            * .context              
    * DataStandardsWales-Observation
        * Cardinality changed from 1..1 to 0..1:
            * .partOf.identifier
    * DataStandardsWales-Observation-Lab Resource
        * Corrected spelling error
* Code Systems:
    * DataStandardsWales-GenderIdentity
        * Trailing space removed from display value
    * DataStandardsWales-Sex
        * Trailing space removed from display value
* Value Set: 
    * DataStandardsWales-GenderIdentity
        * Trailing space removed from display value
    * DataStandardsWales-Sex
        * Trailing space removed from display value
    * DataStandardsWales-Title
        * Code expansion format corrected
* Concept Maps:
    * DataStandardsWales-GenderIdentity-HL7AdministrativeGender Resource
        * Corrected spelling error
        * Changed the targetURI to correct valueset
    * DataStandardsWales-HL7AdministrativeGender-GenderIdentity Resource
        * Changed the targetURI to correct valueset
    * DataStandardsWales-MaritalStatus-UKCorePersonMaritalStatusCode Resource
        * Changed the targetURI to correct valueset
        * Leading space removed from target value
* Extension:
    * DataStandardsWales-MedicationCourseOfTherapyType
        * Change to correct valueset
* Naming Systems:
    * Velindre PAS namespace OID corrected
    * BCUHB Central PAS Identifier corrected inconsistency
* Examples:
    * Organization - Glangwili General Hospital 
        * Removed hospital classification extension
    * Organization - Neath - Port Talbot Hospital 
        * Removed hospital classification extension
* Fixed render issues in ConceptsMaps, CodeSystem, NamingSystem & ValueSet by using HL7 FHIR XML element order
* Spaces removed in NamingSystems name to conform to HL7 as name can be used as id

Guide:
* DataStandardsWales-MedicationDispense
    * Mandatory and Must Support Data Elements list updated to reflect changes made to the profile and correct previously omitted information:
        * Updated the must have list as per current profile settings
        * Updated the must support list as per current profile settings   

### v1.0.0 STU1

* Changes made following feedback from the publication of the pre-release

### v1.0.0 STU1 - pre release

* Changes made in response to the ballot feedback process

### v0.1.1 STU1 - for ballot

* Minor errata to fix asset rendering issues

### v0.1.0 STU1 - for ballot

* First pass review of profiles
* Medication Scenarios
* Improvements to navigation
* Fixed page links and spelling
* Removed duplicate guidance
* References to HL7 or UK Core guidance where necessary


### 0.0.5 - Discovery

Experimental medication profiles were added.


* Immunization
* MedicationAdministration


The following experimental profiles were amended.


* MedicationDispense
* MedicationRequest


### 0.0.4 - Discovery

Experimental medication profiles were added.


* MedicationRequest
* MedicationDispense

A profile can now be designated as "Experimental" to show publishing intent in the near future.

### 0.0.2 & 0.0.3 - Discovery

Various profile drafts and fixes have been added.

### 0.0.1 - Discovery
The initial draft of the Data Standards Wales FHIR Implementation Guide, and should be considered 'under construction'. It contains only the base FHIR 'people and places' administrative resources.

This version is not intended for use, but is published for early comment and feedback.

<div class="container">
    <div class="row">
        <div class="col-md-7 card">
            <h4><b><a href="https://simplifier.net/guide/wales-fhir-implementation-guide-version-history" alt="Wales FHIR Implementation GUide Version History" target="_blank">Wales FHIR Implementation Guide Version History</a></b></h4>
            <p>Detailed description of the implementation guide changes</p>
        </div>
    </div>
</div>