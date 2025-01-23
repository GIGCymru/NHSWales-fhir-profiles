## Example Provenance
Example Provenance resource, including references to related Device and DocumentReference resources. The DocumentReference resource can used to link to the message that triggered the insert or update to the record e.g. an HL7v2 ADT^A31 demographic update message.

Where Device resources are not available in within the data store, logical references can be used (see this {{pagelink:Home/FHIR-Assets/Profiles-and-Extensions/Profiles/Examples/Example-DataStandardsWales-Provenance-Amend-Alt.page.md, text: Provanance}} example)



<div class="tab-wrap">
  <ul class="tab-head">
    <li class="tablink" onclick="openCity(this,'tabtree')" data-target="tabtree">
      Overview
    </li>
    <li class="tablink" onclick="openCity(this,'tabtable')" data-target="tabtable">
      Table
    </li>
    <li class="tablink tab-active" onclick="openCity(this,'tabxml')" data-target="tabxml">
      XML
    </li>    
    <li class="tablink" onclick="openCity(this,'tabjson')" data-target="tabjson">
      JSON
    </li>    
    <li class="tablink" onclick="openCity(this,'tabnarrative')" data-target="tabnarrative">
      Narrative
    </li>
  </ul>
  <div class="tab-main">
    <div id="tabtree" class="tabcontent">
      {{tree:Provenance/Example-DataStandardsWales-Provenance-Amend}}
    </div>
    <div id="tabtable" class="tabcontent">
      {{table:Provenance/Example-DataStandardsWales-Provenance-Amend}}
    </div>       
    <div id="tabxml" class="tabcontent active">      
      {{xml:Provenance/Example-DataStandardsWales-Provenance-Amend}}
    </div>
    <div id="tabjson" class="tabcontent">
      {{json:Provenance/Example-DataStandardsWales-Provenance-Amend}}
    </div>       
    <div id="tabnarrative" class="tabcontent">
      {{narrative:Provenance/Example-DataStandardsWales-Provenance-Amend}}
    </div>  
  </div>
</div>