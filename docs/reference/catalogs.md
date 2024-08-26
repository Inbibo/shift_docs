# Catalogs

Catalogs are libraries of operators that define and extend Shift's capabilities, as they provide the specialized nodes for different areas of development and automatization. 


Shift comes with six native catalogs that contain the necessary nodes to start building a workflow:

- **Constants catalog**: Provides operators to work with standard Python type objects, such as booleans or strings.
- **Standard catalog**: Provides operators to work with standard Python operations. It provides logic to perform [loop iterations](../reference/nodes/iteration.md) and create [scriptable Python nodes](../reference/nodes/python_script.md). It also includes operators to read/write JSON files, operate with lists, strings, dictionaries and more.
- **FileSystem catalog**: Provides operators to work with the OS filesystem and environment variables. It includes operators to perform file & directory creation and manipulation and more.
- **Regex catalog**: Provides operators to work with regular expressions and functions.
- **CreativeSoftware catalog**: Provides operators to work with Digital Content Creation softwares. It includes operators for scene management, geometry handling, node graph manipulation and more, across popular DCC tools like Maya, Houdini, Blender, and Nuke.
- **Workflow catalog**: Provides operators to manage and nest Shift workflows. It includes operators to input and output data, store [variables](../reference/nodes/variables.md) and execute [sub-workflows](../reference/nodes/workflow.md).

>[!NOTE]
> Shift also comes with a native catalog for Deadline. For more information about Shift's integration in Deadline and how to use this catalog, please refer to the [Deadline Integration](../integration_resources/deadline.md) documentation.

### Custom Catalogs

Catalogs are scripted Python files that define a list of operators classes and their execution logic. To learn more about how to write a custom catalog, please refer to the [developer's guide](../reference/dev_help/developers_guide/#create-a-catalog) for catalogs. 


## The Catalog Manager

The Catalog Manager is used to inspect the current available catalogs for Shift, add new ones, and load or unload them. 


TO BE DEFINED BY ISSUE #16
