<div class="warning"><span class="ImplementWarn"></span></div>

## {{page-title}}
An extension to capture attributes of a document that are not explicitly addressed within DocumentReference.  Intended for use by exception only to capture data important for specific document types e.g.clinical trial code for cancer-related documents.  May be used more extensively for legacy documents.

### Purpose
This extension extends the DocumentReference resource to capture document metadata that is not represented by elements of the DocumentReference resource or its referenced resources.  The list of attributes is constrained to avoid proliferation of unstructured document emtadata.

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
      {{tree:extensiondatastandardswalesdocumentattribute, snapshot}}
    </div>
    <div id="tabeg" class="tabcontent">
      <list>
         <li>Currently under development</li>
      </list>
    </div>
  </div>
</div>