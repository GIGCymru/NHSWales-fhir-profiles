<div class="warning"><span class="ImplementWarn"></span></div>

## {{page-title}}
An extension to capture a participant who has authenticated the accuracy of the document. (Backport from FHIR R5.)

### Purpose
This extension extends the DocumentReference resource to capture the document attestation including who, when and mode of attestation e.g. professional. This extension replaces the use of authenticator in the Data Standards Wales uses of DocumentReference at FHIR R4.

### Context of Use
This extension may be used on the following profile(s):
- DocumentReference

### Formal Views of Extension Content
<div class="tab-wrap">
  <ul class="tab-head">
    <li class="tablink tab-active" onclick="openCity(this,'tabsnap')" data-target="tabsnap">
      Snapshot View
    </li>
    <li class="tablink" onclick="openCity(this,'tabeg')" data-target="tabeg">
      Example View
    </li>
  </ul>
  <div class="tab-main">
    <div id="tabsnap" class="tabcontent active">      
      {{tree:extensiondatastandardswalesdocumentattester, snapshot}}
    </div>
    <div id="tabeg" class="tabcontent">
      <list>
         <li>Currently under development</li>
      </list>
    </div>
  </div>
</div>