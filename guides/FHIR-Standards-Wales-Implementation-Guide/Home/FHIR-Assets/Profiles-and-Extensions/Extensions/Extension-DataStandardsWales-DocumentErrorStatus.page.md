<div class="warning"><span class="ImplementWarn"></span></div>

## {{page-title}}
An extension to capture the error status of a document

### Purpose
This extension extends the DocumentReference resource to capture the distinct error status that applies to a document "entered-in-error".  The values supported are restricted by {{pagelink:ValueSet-DataStandardsWales-DocumentErrorStatus}}.

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
      {{tree:extensiondatastandardswalesdocumenterrorstatus, snapshot}}
    </div>
    <div id="tabeg" class="tabcontent">
      <list>
         <li>Currently under development</li>
      </list>
    </div>
  </div>
</div>