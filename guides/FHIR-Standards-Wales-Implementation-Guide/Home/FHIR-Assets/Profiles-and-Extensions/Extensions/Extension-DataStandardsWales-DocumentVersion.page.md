<div class="warning"><span class="ImplementWarn"></span></div>

## {{page-title}}
An extension to capture an explicitly assigned identifer of a variation of the content in the DocumentReference. (Backport from FHIR R5.)

### Purpose
This extension extends the DocumentReference resource to capture a business version identifier (not a resource version id).  It can be used to store the SetSequenceNumber of a document from the Welsh Care Records Service. 

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
      {{tree:extensiondatastandardswalesdocumentversion, snapshot}}
    </div>
    <div id="tabeg" class="tabcontent">
      <list>
         <li>Currently under development</li>
      </list>
    </div>
  </div>
</div>