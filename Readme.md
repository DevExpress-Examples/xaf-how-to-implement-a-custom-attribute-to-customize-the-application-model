<!-- default badges list -->
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E1679)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->

# XAF - How to implement a custom attribute to customize the Application Model

This example demonstrates how to create a custom attribute and remove a property from the [Application Model](https://docs.devexpress.com/eXpressAppFramework/112579/ui-construction/application-model-ui-settings-storage)'s `DetailView.Items` and `ListView.Columns` nodes.
In this case, the properties marked with this attribute are removed from views.

## Implementation Details

To implement this functionality, the `IModelMember` interface is extended with the `IRemovedFromViewInfo` interface that contains the `IsRemovedFromViewInfo` property. The value of this property is calculated based on the value of the custom attribute we created (`RemoveFromViewInfoAttribute`) and applied to the persistent class via the domain logic (`RemovedFromViewInfoLogic`). The `IRemovedFromViewInfo.IsRemovedFromViewInfo` property is used by the model node generator updater (`ViewsNodesGeneratorUpdater`) to remove certain view items and columns from detail and list views. 

This example demonstrates three techniques: how to extend the application model with additional properties, define default model values via domain logic, and modify the default model via the model node generator updater.

## Files to Review

* [Contact.cs](CS/CustomAttributeSolution/CustomAttributeSolution.Module/BusinessObjects/Contact.cs)
* [Module.cs](CS/CustomAttributeSolution/CustomAttributeSolution.Module/Module.cs)
* [RemoveFromViewInfoAttribute.cs](CS/CustomAttributeSolution/CustomAttributeSolution.Module/RemoveFromViewInfoAttribute.cs)


## Documentation 

* [Create Additional ListView Nodes in Code Using a Generator Updater](https://docs.devexpress.com/eXpressAppFramework/113315/ui-construction/application-model-ui-settings-storage/customize-application-model-in-code/create-additional-list-view-nodes-in-code-using-a-generator-updater)
* [Add Custom Nodes and Properties to the Application Model in Code](https://docs.devexpress.com/eXpressAppFramework/404125/ui-construction/application-model-ui-settings-storage/modify-application-model/add-nodes-and-node-properties-to-app-model)
