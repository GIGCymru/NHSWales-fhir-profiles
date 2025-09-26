<div class="warning"><span class="ImplementWarn"></span></div>

## {{page-title}}
An extension to capture the error status of a document

### Purpose
This extension extends the DocumentReference resource to capture the distinct error status that applies to a document "entered-in-error", which may need to be considered by applications retrieving the document to influence its display and processing options.  It distinguishes between documents that are potentially misfiled, documents confirmed as misfiled and documents explicitly revoked.

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
      {{tree:extensiondatastandardswalesdocumenterrorstatus, snapshot}}
    </div>
    <div id="tabeg" class="tabcontent">
      <list>
         <li>Currently under development</li>
      </list>
    </div>
  </div>
</div>