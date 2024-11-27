## {{page-title}}
The diagram below shows the relationship a Provenance resource, and the systems (or agents) an entities responsible for the data update. 

{{render:Diagrams/LogicalModel-Provenance.drawio.png}}


Note that in the model above, the Device resource is used to indicate the systems involved in the data update. If these resources do not exist within the datastore, then a logical reference may be used instead (see example 2) 

The DocumentReference resource can be used to provide a link to the message that can be included as an attachment or via a URL link.