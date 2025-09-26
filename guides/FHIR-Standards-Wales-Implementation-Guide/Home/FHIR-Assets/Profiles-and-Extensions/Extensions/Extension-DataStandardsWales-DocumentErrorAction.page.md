<div class="warning"><span class="ImplementWarn"></span></div>

## {{page-title}}
This extension provides outline data for an action performed as part of a document error workflow e.g. document misfile proposed.

### Purpose
This extension extends the DocumentReference resource to capture the metadata (who, when and reason) associated with an explicit action involved in identifying the document as no longer valid for clinical use.  This extension may for example record the action of one user in marking a document as potentially misfiled against the wrong patient, or the decision of another user to accept or reject the proposed misfile. It can also be used to capture an explicit actions to revoke a document, such as patient revocation of a do not attempt resuscitation (DNAR) instruction.

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
      {{tree:extensiondatastandardswalesdocumenterroraction, snapshot}}
    </div>
    <div id="tabeg" class="tabcontent">
      <list>
         <li>Currently under development</li>
      </list>
    </div>
  </div>
</div>