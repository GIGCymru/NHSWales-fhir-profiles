<div class="col-md-6 guidancesidepanel">
{{index:Home/API-Guidance}} 
</div>
 
<div class="col-md-18">

<div class="warning"><b>Important:</b> All content in this FHIR Implementation Guide is under development</div>


# {{page-title}}

## Introduction
This section supplies guidance on how to interact with the WRRS FHIR API.

## Supported interactions
The table below gives an overview of the FHIR resources and interations supported in the WRRS FHIR API, it is divided into the following columns

 - **Resource** - The supported FHIR resource from the FHIR standard
 - **Profile** - The FHIR profile used in the API specifying a set of constraints and/or extensions on the base resource
 - **Interaction Supported** - The RESTful HTTP methods the API supports for that resource
 - **Includes Supported** - What additional resources can be included as part of a search result bundle for the specified resource, more details
 - **FHIR Parameters Supported** - What Querystring parameters can be used to search against the specified resource type

## API Interaction Overview

<table id="t1" class="table table-striped">
    <thead>
        <tr>
            <th title="Resource">Resource</th>
            <th title="profile">Profiles</th>
            <th title="Interactions Supported">Includes Supported</th>
            <th title="Includes Supported">Includes Supported</th>
            <th title="FHIR Parameters Supported">Parameters</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>DiagnosticReport</td>
            <td>DataStandardsWales-DiagnosticReport</br></br>DataStandardsWales-DiagnosticReport-Lab</td>
            <td>GET</td>
            <td>
                <table id="t2">
                    <tbody>
                        <tr>
                            <td>DiagnosticReport:performer</td>
                        </tr>
                        <tr>
                            <td>DiagnosticReport:result</td>
                        </tr>
                        <tr>
                            <td>DiagnosticReport:subject</td>
                        </tr>
                        <tr>
                            <td>DiagnosticReport:patient</td>
                        </tr>
                    </tbody>
                </table>
            </td>
            <td>
                <table id="t3" class="table table-bordered">
                    <thead>
                        <tr>
                            <td class="typeheader" colspan="4"><a class="typeheader"
                                    onclick="return toggle('t3');"><span class="arrow-up"
                                        id="t3ud"></span>Supported Parameters (16 items)</a><span class="meta" />
                            </td>
                        </tr>
                        <tr>
                            <th title="System.String">name</th>
                            <th title="System.String">type</th>
                            <th title="System.String">definition</th>
                            <th title="System.String">documentation</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>_count</td>
                            <td>number</td>
                            <td></td>
                            <td>The number of resources returned per page</td>
                        </tr>
                        <tr>
                            <td>_format</td>
                            <td>string</td>
                            <td></td>
                            <td>Specify the returned format of the payload response</td>
                        </tr>
                        <tr>
                            <td>_has</td>
                            <td>string</td>
                            <td></td>
                            <td>Enables querying a reverse chain</td>
                        </tr>
                        <tr>
                            <td>_id</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-id</td>
                            <td>Logical id of this artifact</td>
                        </tr>
                        <tr>
                            <td>_lastUpdated</td>
                            <td>date</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-lastUpdated</td>
                            <td>When the resource version last changed</td>
                        </tr>
                        <tr>
                            <td>_profile</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-profile</td>
                            <td>Profiles this resource claims to conform to</td>
                        </tr>
                        <tr>
                            <td>_security</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-security</td>
                            <td>Security Labels applied to this resource</td>
                        </tr>
                        <tr>
                            <td>_source</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-source</td>
                            <td>Identifies where the resource comes from</td>
                        </tr>
                        <tr>
                            <td>_tag</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-tag</td>
                            <td>Tags applied to this resource</td>
                        </tr>
                        <tr>
                            <td>category</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/DiagnosticReport-category</td>
                            <td>Which diagnostic discipline/department created the report</td>
                        </tr>
                        <tr>
                            <td>code</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/clinical-code</td>
                            <td style="min-width:30em">The code for
                                the report, as opposed to codes for the atomic results, which are the names on
                                the observation resource referred to from the result</td>
                        </tr>
                        <tr>
                            <td>issued</td>
                            <td>date</td>
                            <td>http://hl7.org/fhir/SearchParameter/DiagnosticReport-issued</td>
                            <td>When the report was issued</td>
                        </tr>
                        <tr>
                            <td>patient</td>
                            <td>reference</td>
                            <td>http://hl7.org/fhir/SearchParameter/clinical-patient</td>
                            <td style="min-width:30em">The subject of the
                                report if a patient</td>
                        </tr>
                        <tr>
                            <td>performer</td>
                            <td>reference</td>
                            <td>http://hl7.org/fhir/SearchParameter/DiagnosticReport-performer</td>
                            <td>Who is responsible for the report</td>
                        </tr>
                        <tr>
                            <td>result</td>
                            <td>reference</td>
                            <td>http://hl7.org/fhir/SearchParameter/DiagnosticReport-result</td>
                            <td>Link to an atomic result (observation resource)</td>
                        </tr>
                        <tr>
                            <td>subject</td>
                            <td>reference</td>
                            <td>http://hl7.org/fhir/SearchParameter/DiagnosticReport-subject</td>
                            <td>The subject of the report</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
        <tr>
            <td>ImagingStudy</td>
            <td>DataStandardsWales-ImagingStudy</td>
            <td>GET</td>
            <td></td>
            <td>
                <table id="t5"  class="table table-bordered">
                    <thead>
                        <tr>
                            <td class="typeheader" colspan="4"><a class="typeheader"
                                    onclick="return toggle('t5');"><span class="arrow-up"
                                        id="t5ud"></span>Supported Parameters (9 items)</a><span class="meta" />
                            </td>
                        </tr>
                        <tr>
                            <th title="System.String">name</th>
                            <th title="System.String">type</th>
                            <th title="System.String">definition</th>
                            <th title="System.String">documentation</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>_count</td>
                            <td>number</td>
                            <td></td>
                            <td>The number of resources returned per page</td>
                        </tr>
                        <tr>
                            <td>_format</td>
                            <td>string</td>
                            <td></td>
                            <td>Specify the returned format of the payload response</td>
                        </tr>
                        <tr>
                            <td>_has</td>
                            <td>string</td>
                            <td></td>
                            <td>Enables querying a reverse chain</td>
                        </tr>
                        <tr>
                            <td>_id</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-id</td>
                            <td>Logical id of this artifact</td>
                        </tr>
                        <tr>
                            <td>_lastUpdated</td>
                            <td>date</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-lastUpdated</td>
                            <td>When the resource version last changed</td>
                        </tr>
                        <tr>
                            <td>_profile</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-profile</td>
                            <td>Profiles this resource claims to conform to</td>
                        </tr>
                        <tr>
                            <td>_security</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-security</td>
                            <td>Security Labels applied to this resource</td>
                        </tr>
                        <tr>
                            <td>_source</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-source</td>
                            <td>Identifies where the resource comes from</td>
                        </tr>
                        <tr>
                            <td>_tag</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-tag</td>
                            <td>Tags applied to this resource</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
        <tr>
            <td>Observation</td>
            <td>DataStandardsWales-Observation-Lab</td>
            <td>GET</td>
            <td>
                <table id="t6">
                    <tbody>
                        <tr>
                            <td>Observation:subject</td>
                        </tr>
                        <tr>
                            <td>Observation:patient</td>
                        </tr>
                    </tbody>
                </table>
            </td>
            <td>
                <table id="t7" class="table table-bordered">
                    <thead>
                        <tr>
                            <td class="typeheader" colspan="4"><a class="typeheader"
                                    onclick="return toggle('t7');"><span class="arrow-up"
                                        id="t7ud"></span>Supported Parameters (12 items)</a><span class="meta" />
                            </td>
                        </tr>
                        <tr>
                            <th title="System.String">name</th>
                            <th title="System.String">type</th>
                            <th title="System.String">definition</th>
                            <th title="System.String">documentation</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>_count</td>
                            <td>number</td>
                            <td></td>
                            <td>The number of resources returned per page</td>
                        </tr>
                        <tr>
                            <td>_format</td>
                            <td>string</td>
                            <td></td>
                            <td>Specify the returned format of the payload response</td>
                        </tr>
                        <tr>
                            <td>_has</td>
                            <td>string</td>
                            <td></td>
                            <td>Enables querying a reverse chain</td>
                        </tr>
                        <tr>
                            <td>_id</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-id</td>
                            <td>Logical id of this artifact</td>
                        </tr>
                        <tr>
                            <td>_lastUpdated</td>
                            <td>date</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-lastUpdated</td>
                            <td>When the resource version last changed</td>
                        </tr>
                        <tr>
                            <td>_profile</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-profile</td>
                            <td>Profiles this resource claims to conform to</td>
                        </tr>
                        <tr>
                            <td>_security</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-security</td>
                            <td>Security Labels applied to this resource</td>
                        </tr>
                        <tr>
                            <td>_source</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-source</td>
                            <td>Identifies where the resource comes from</td>
                        </tr>
                        <tr>
                            <td>_tag</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-tag</td>
                            <td>Tags applied to this resource</td>
                        </tr>
                        <tr>
                            <td>code</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/clinical-code</td>
                            <td style="min-width:30em"> The code of the
                                observation type</td>
                        </tr>
                        <tr>
                            <td>patient</td>
                            <td>reference</td>
                            <td>http://hl7.org/fhir/SearchParameter/clinical-patient</td>
                            <td style="min-width:30em">*
                                    The subject that the observation is about (if
                                patient)</td>
                        </tr>
                        <tr>
                            <td>subject</td>
                            <td>reference</td>
                            <td>http://hl7.org/fhir/SearchParameter/Observation-subject</td>
                            <td>The subject that the observation is about</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
        <tr>
            <td>Organization</td>
            <td>DataStandardsWales-Organization</td>
            <td>GET</td>
            <td></td>
            <td>
                <table id="t9" class="table table-bordered">
                    <thead>
                        <tr>
                            <td class="typeheader" colspan="4"><a class="typeheader"
                                    onclick="return toggle('t9');"><span class="arrow-up"
                                        id="t9ud"></span>Supported Parameters (10 items)</a><span class="meta" />
                            </td>
                        </tr>
                        <tr>
                            <th title="System.String">name</th>
                            <th title="System.String">type</th>
                            <th title="System.String">definition</th>
                            <th title="System.String">documentation</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>_count</td>
                            <td>number</td>
                            <td></td>
                            <td>The number of resources returned per page</td>
                        </tr>
                        <tr>
                            <td>_format</td>
                            <td>string</td>
                            <td></td>
                            <td>Specify the returned format of the payload response</td>
                        </tr>
                        <tr>
                            <td>_has</td>
                            <td>string</td>
                            <td></td>
                            <td>Enables querying a reverse chain</td>
                        </tr>
                        <tr>
                            <td>_id</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-id</td>
                            <td>Logical id of this artifact</td>
                        </tr>
                        <tr>
                            <td>_lastUpdated</td>
                            <td>date</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-lastUpdated</td>
                            <td>When the resource version last changed</td>
                        </tr>
                        <tr>
                            <td>_profile</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-profile</td>
                            <td>Profiles this resource claims to conform to</td>
                        </tr>
                        <tr>
                            <td>_security</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-security</td>
                            <td>Security Labels applied to this resource</td>
                        </tr>
                        <tr>
                            <td>_source</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-source</td>
                            <td>Identifies where the resource comes from</td>
                        </tr>
                        <tr>
                            <td>_tag</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-tag</td>
                            <td>Tags applied to this resource</td>
                        </tr>
                        <tr>
                            <td>identifier</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Organization-identifier</td>
                            <td>Any identifier for the organization (not the accreditation issuer's identifier)
                            </td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
        <tr>
            <td>Patient</td>
            <td>DataStandardsWales-Patient</td>
            <td>GET</td>
            <td></td>
            <td>
                <table id="t11" class="table table-bordered">
                    <thead>
                        <tr>
                            <td class="typeheader" colspan="4"><a class="typeheader"
                                    onclick="return toggle('t11');"><span class="arrow-up"
                                        id="t11ud"></span>Supported Parameters (15 items)</a><span class="meta" />
                            </td>
                        </tr>
                        <tr>
                            <th title="System.String">name</th>
                            <th title="System.String">type</th>
                            <th title="System.String">definition</th>
                            <th title="System.String">documentation</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>_count</td>
                            <td>number</td>
                            <td></td>
                            <td>The number of resources returned per page</td>
                        </tr>
                        <tr>
                            <td>_format</td>
                            <td>string</td>
                            <td></td>
                            <td>Specify the returned format of the payload response</td>
                        </tr>
                        <tr>
                            <td>_has</td>
                            <td>string</td>
                            <td></td>
                            <td>Enables querying a reverse chain</td>
                        </tr>
                        <tr>
                            <td>_id</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-id</td>
                            <td>Logical id of this artifact</td>
                        </tr>
                        <tr>
                            <td>_lastUpdated</td>
                            <td>date</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-lastUpdated</td>
                            <td>When the resource version last changed</td>
                        </tr>
                        <tr>
                            <td>_profile</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-profile</td>
                            <td>Profiles this resource claims to conform to</td>
                        </tr>
                        <tr>
                            <td>_security</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-security</td>
                            <td>Security Labels applied to this resource</td>
                        </tr>
                        <tr>
                            <td>_source</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-source</td>
                            <td>Identifies where the resource comes from</td>
                        </tr>
                        <tr>
                            <td>_tag</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-tag</td>
                            <td>Tags applied to this resource</td>
                        </tr>
                        <tr>
                            <td>address</td>
                            <td>string</td>
                            <td>http://hl7.org/fhir/SearchParameter/individual-address</td>
                            <td style="min-width:30em">
                                * A server defined search that may match any of the
                                string fields in the Address, including line, city, district, state, country,
                                postalCode, and/or text<br />A server defined search
                                that may match any of the string fields in the Address, including line, city,
                                district, state, country, postalCode, and/or text</td>
                        </tr>
                        <tr>
                            <td>address-postalcode</td>
                            <td>string</td>
                            <td>http://hl7.org/fhir/SearchParameter/individual-address-postalcode</td>
                            <td style="min-width:30em">
                                * A postalCode specified in an address</td>
                        </tr>
                        <tr>
                            <td>birthdate</td>
                            <td>date</td>
                            <td>http://hl7.org/fhir/SearchParameter/individual-birthdate</td>
                            <td style="min-width:25em">
                                * The patient's date of birth</td>
                        </tr>
                        <tr>
                            <td>family</td>
                            <td>string</td>
                            <td>http://hl7.org/fhir/SearchParameter/individual-family</td>
                            <td style="min-width:20em">
                                * A portion of the family name of the patient</td>
                        </tr>
                        <tr>
                            <td>given</td>
                            <td>string</td>
                            <td>http://hl7.org/fhir/SearchParameter/individual-given</td>
                            <td style="min-width:19em">
                                * A portion of the given name of the patient</td>
                        </tr>
                        <tr>
                            <td>identifier</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Patient-identifier</td>
                            <td>A patient identifier</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
        <tr>
            <td>Practitioner</td>
            <td>DataStandardsWales-Practitioner</td>
            <td>GET</td>
            <td></td>
            <td>
                <table id="t13" class="table table-bordered">
                    <thead>
                        <tr>
                            <td class="typeheader" colspan="4"><a class="typeheader"
                                    onclick="return toggle('t13');"><span class="arrow-up"
                                        id="t13ud"></span>Supported Parameters (9 items)</a><span class="meta" />
                            </td>
                        </tr>
                        <tr>
                            <th title="System.String">name</th>
                            <th title="System.String">type</th>
                            <th title="System.String">definition</th>
                            <th title="System.String">documentation</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>_count</td>
                            <td>number</td>
                            <td></td>
                            <td>The number of resources returned per page</td>
                        </tr>
                        <tr>
                            <td>_format</td>
                            <td>string</td>
                            <td></td>
                            <td>Specify the returned format of the payload response</td>
                        </tr>
                        <tr>
                            <td>_has</td>
                            <td>string</td>
                            <td></td>
                            <td>Enables querying a reverse chain</td>
                        </tr>
                        <tr>
                            <td>_id</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-id</td>
                            <td>Logical id of this artifact</td>
                        </tr>
                        <tr>
                            <td>_lastUpdated</td>
                            <td>date</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-lastUpdated</td>
                            <td>When the resource version last changed</td>
                        </tr>
                        <tr>
                            <td>_profile</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-profile</td>
                            <td>Profiles this resource claims to conform to</td>
                        </tr>
                        <tr>
                            <td>_security</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-security</td>
                            <td>Security Labels applied to this resource</td>
                        </tr>
                        <tr>
                            <td>_source</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-source</td>
                            <td>Identifies where the resource comes from</td>
                        </tr>
                        <tr>
                            <td>_tag</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-tag</td>
                            <td>Tags applied to this resource</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
        <tr>
            <td>ServiceRequest</td>
            <td>DataStandardsWales-ServiceRequest</td>
            <td>GET</td>
            <td>
                <table id="t14">
                    <tbody>
                        <tr>
                            <td>ServiceRequest:specimen</td>
                        </tr>
                        <tr>
                            <td>ServiceRequest:subject</td>
                        </tr>
                        <tr>
                            <td>ServiceRequest:patient</td>
                        </tr>
                    </tbody>
                </table>
            </td>
            <td>
                <table id="t15" class="table table-bordered">
                    <thead>
                        <tr>
                            <td class="typeheader" colspan="4"><a class="typeheader"
                                    onclick="return toggle('t15');"><span class="arrow-up"
                                        id="t15ud"></span>Supported Parameters (16 items)</a><span class="meta" />
                            </td>
                        </tr>
                        <tr>
                            <th title="System.String">name</th>
                            <th title="System.String">type</th>
                            <th title="System.String">definition</th>
                            <th title="System.String">documentation</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>_count</td>
                            <td>number</td>
                            <td></td>
                            <td>The number of resources returned per page</td>
                        </tr>
                        <tr>
                            <td>_format</td>
                            <td>string</td>
                            <td></td>
                            <td>Specify the returned format of the payload response</td>
                        </tr>
                        <tr>
                            <td>_has</td>
                            <td>string</td>
                            <td></td>
                            <td>Enables querying a reverse chain</td>
                        </tr>
                        <tr>
                            <td>_id</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-id</td>
                            <td>Logical id of this artifact</td>
                        </tr>
                        <tr>
                            <td>_lastUpdated</td>
                            <td>date</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-lastUpdated</td>
                            <td>When the resource version last changed</td>
                        </tr>
                        <tr>
                            <td>_profile</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-profile</td>
                            <td>Profiles this resource claims to conform to</td>
                        </tr>
                        <tr>
                            <td>_security</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-security</td>
                            <td>Security Labels applied to this resource</td>
                        </tr>
                        <tr>
                            <td>_source</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-source</td>
                            <td>Identifies where the resource comes from</td>
                        </tr>
                        <tr>
                            <td>_tag</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-tag</td>
                            <td>Tags applied to this resource</td>
                        </tr>
                        <tr>
                            <td>authored</td>
                            <td>date</td>
                            <td>http://hl7.org/fhir/SearchParameter/ServiceRequest-authored</td>
                            <td>Date request signed</td>
                        </tr>
                        <tr>
                            <td>category</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/ServiceRequest-category</td>
                            <td>Classification of service</td>
                        </tr>
                        <tr>
                            <td>code</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/clinical-code</td>
                            <td style="min-width:30em"> What is being
                                requested/ordered</td>
                        </tr>
                        <tr>
                            <td>identifier</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/clinical-identifier</td>
                            <td style="min-width:30em"> Identifiers
                                assigned to this order</td>
                        </tr>
                        <tr>
                            <td>patient</td>
                            <td>reference</td>
                            <td>http://hl7.org/fhir/SearchParameter/clinical-patient</td>
                            <td style="min-width:30em"> Search by subject - a
                                patient</td>
                        </tr>
                        <tr>
                            <td>specimen</td>
                            <td>reference</td>
                            <td>http://hl7.org/fhir/SearchParameter/ServiceRequest-specimen</td>
                            <td>Specimen to be tested</td>
                        </tr>
                        <tr>
                            <td>subject</td>
                            <td>reference</td>
                            <td>http://hl7.org/fhir/SearchParameter/ServiceRequest-subject</td>
                            <td>Search by subject</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
        <tr>
            <td>Specimen</td>
            <td>DataStandardsWales-Specimen</td>
            <td>GET</td>
            <td>
                <table id="t16">
                    <tbody>
                        <tr>
                            <td>Specimen:patient</td>
                        </tr>
                        <tr>
                            <td>Specimen:subject</td>
                        </tr>
                    </tbody>
                </table>
            </td>
            <td>
                <table id="t17" class="table table-bordered">
                    <thead>
                        <tr>
                            <td class="typeheader" colspan="4"><a class="typeheader"
                                    onclick="return toggle('t17');"><span class="arrow-up"
                                        id="t17ud"></span>Supported Parameters (16 items)</a><span class="meta" />
                            </td>
                        </tr>
                        <tr>
                            <th title="System.String">name</th>
                            <th title="System.String">type</th>
                            <th title="System.String">definition</th>
                            <th title="System.String">documentation</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>_count</td>
                            <td>number</td>
                            <td></td>
                            <td>The number of resources returned per page</td>
                        </tr>
                        <tr>
                            <td>_format</td>
                            <td>string</td>
                            <td></td>
                            <td>Specify the returned format of the payload response</td>
                        </tr>
                        <tr>
                            <td>_has</td>
                            <td>string</td>
                            <td></td>
                            <td>Enables querying a reverse chain</td>
                        </tr>
                        <tr>
                            <td>_id</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-id</td>
                            <td>Logical id of this artifact</td>
                        </tr>
                        <tr>
                            <td>_lastUpdated</td>
                            <td>date</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-lastUpdated</td>
                            <td>When the resource version last changed</td>
                        </tr>
                        <tr>
                            <td>_profile</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-profile</td>
                            <td>Profiles this resource claims to conform to</td>
                        </tr>
                        <tr>
                            <td>_security</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-security</td>
                            <td>Security Labels applied to this resource</td>
                        </tr>
                        <tr>
                            <td>_source</td>
                            <td>uri</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-source</td>
                            <td>Identifies where the resource comes from</td>
                        </tr>
                        <tr>
                            <td>_tag</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Resource-tag</td>
                            <td>Tags applied to this resource</td>
                        </tr>
                        <tr>
                            <td>bodysite</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Specimen-bodysite</td>
                            <td>The code for the body site from where the specimen originated</td>
                        </tr>
                        <tr>
                            <td>collected</td>
                            <td>date</td>
                            <td>http://hl7.org/fhir/SearchParameter/Specimen-collected</td>
                            <td>The date the specimen was collected</td>
                        </tr>
                        <tr>
                            <td>identifier</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Specimen-identifier</td>
                            <td>The unique identifier associated with the specimen</td>
                        </tr>
                        <tr>
                            <td>patient</td>
                            <td>reference</td>
                            <td>http://hl7.org/fhir/SearchParameter/Specimen-patient</td>
                            <td>The patient the specimen comes from</td>
                        </tr>
                        <tr>
                            <td>status</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Specimen-status</td>
                            <td>available | unavailable | unsatisfactory | entered-in-error</td>
                        </tr>
                        <tr>
                            <td>subject</td>
                            <td>reference</td>
                            <td>http://hl7.org/fhir/SearchParameter/Specimen-subject</td>
                            <td>The subject of the specimen</td>
                        </tr>
                        <tr>
                            <td>type</td>
                            <td>token</td>
                            <td>http://hl7.org/fhir/SearchParameter/Specimen-type</td>
                            <td>The specimen type</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

</div>