<div class="warning"><span class="ImplementWarn"></span></div>

## {{page-title}}
This extension provides outline data for an action performed as part of a document error workflow e.g. document misfile proposed.

### Purpose
This extension extends the DocumentReference resource to captures the metadata (who, when and reason) associated with an explicit action involved in identifying the document as no longer valid for clinical use.  This extension may for example record the action of one user in marking a document as potentially misfiled against the wrong patient, or the outcome of the misfile review by another user, as an acceptance or rejection of the proposed misfile.  The error workflow actions supported are restricted by {{pagelink:ValueSet-FHIRStandardsWales-DocumentErrorAction}}.

### Context of Use
This extension may be used on the following profile(s):
* {{pagelink:DataStandardsWales-DocumentReference}}

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
      {{tree:extensiondatastandardswalesdocumenterroraction, snapshot}}
    </div>
    <div id="tabeg" class="tabcontent">
      <list>
         <li>Currently under development</li>
      </list>
    </div>
  </div>
</div>