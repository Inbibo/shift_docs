# Plugins

Shift supports the integration of custom Plugins. Shift Plugins are Qt based UIs which can interact with Shift to display additional information, perform actions or modify the behaviour of the application.

## Shift Native Plugins

Shift ships with two plugins which can be found in the *Tools* section in the top menu bar. The desired Plugin can be opened by clicking on the corresponding entry.

Once a Plugin is opened, the Shift UI can be customized with the best suited layout.

The *Operators List* Plugin helps us visualize the list of operators in the workflow and shows the their current progress.

![Opening a Plugin](/images/opening_a_plugin.gif)

The *Variables Browser* allows users to parse the workflow variables currently set and check their content. This is especially helpful in large workflows where it is easy to lose track of which nodes were previously executed. This Plugin also allows to delete specific workflow variables set while working on a workflow. To do that `Right-click` on the variable entry to delete and select the *Delete* option.


![Variables Browser Plugin](/images/variables_browser_plugin.gif)