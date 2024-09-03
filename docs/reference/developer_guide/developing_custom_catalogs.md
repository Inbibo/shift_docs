# Developing Custom Catalogs

In Shift it is possible to create customized catalogs with operators tailored for specific use cases and softwares.

## Writing a Catalog

Custom catalogs are written in Python and include a global variable called `catalog`. This variable is a Python dictionary containing the information for the catalog, such as a description, version and authors. Additionally, this dictionary will define the list of operator classes included in the catalog.

**Catalog Dictionary Example**
<pre style="margin: 10px 0; padding: 10px;">
  <code style="white-space: pre">
catalog = {"Description": "This catalog includes fundamental Python type operators.",
          "Version": "1.0.0",
          "Author": "Shift's development team", 
          "Operators":[[String,  []],
                        [Integer, []],
                        [Float,   []],
                        [Bool,    []]]}
  </code>
</pre>

>[!NOTE]
> The *Operators* list from the `catalog` is a list of lists containing two elements. The first one corresponds to the operator class, and the second one is a list of compatible hosts for the operator. If no host is specified, the node will be usable in any context. For instance, if the second element is `["maya", "houdini"]` the operator will be only available for those DCC's. Refer to [Integrations & Resources](../../integration_resources/integrations_resources.md) for more information.

There are two ways of adding a custom catalog to Shift:

- **As a User Catalog**: Use the [Catalog Manager](../catalogs/#the-catalog-manager) to source the catalog file and add it to Shift. This catalog is saved in the user preferences.
- **As an Environment Catalog**: Add the **path to the directory** containing the catalog file to the `SHIFT_CATALOG_PATH` environment variable. All files in this path containing a `catalog` object will be identified as custom catalogs and loaded by Shift.

## Operator Syntax

All Shift operators inherit from the `SOperator` Shift's Python class. To write a custom operator, the `__init__` and `execute` methods must be overwritten. 

Here is an example of an operator class syntax:

<pre style="margin: 10px 0; padding: 10px;">
  <code style="white-space: pre">
from shift.core.workflow import SOperator
from shift.core.workflow import SPlug
from shift.core.constants import SType
from shift.core.constants import SDirection

class MyOperator(SOperator):
    """ The docstring provided for the SOperator class will be use as the operator's description when inspecting a node's information. 
    It is recommended to write a detailed description of the operator's behavior alongside the required inputs and outputs here.
  
    """
    def __init__(self, code, parent=None):

        super(self.__class__, self).__init__(code, parent)

        inPlug1 = SPlug(code="input1",
                      value=0,
                      type=SType.kInt,
                      direction=SDirection.kIn,
                      parent=self)

        inPlug2 = SPlug(code="input2",
                      value=0,
                      type=SType.kInt,
                      direction=SDirection.kIn,
                      parent=self)

        outPlug = SPlug(code="output",
                      value=0,
                      type=SType.kInt,
                      direction=SDirection.kOut,
                      parent=self)

        self.addPlug(inPlug1)
        self.addPlug(inPlug2)
        self.addPlug(outPlug)

    def execute(self, force=False):

        input1 = self.getPlug("input1", SDirection.kIn).value()
        input2 = self.getPlug("input2", SDirection.kOut).value()

        output = input1 * input2

        self.getPlug("output").setValue(output)
        super(self.__class__, self).execute(force)
  </code>
</pre>

The `SOperator` constructor method takes care of initializing the plug objects and adding them to the operator. Each plug must be initialized specifying:
- A unique code name, which will correspond to the name displayed in the UI.
- A value, which will correspond to the value the plug is initialized with.
- A type, which will define the behaviour of the plug when translating the provided inputs to a Python object. Check the `SType` class in Shift's API for more information.
- A direction which can be either `SDirection.kIn` or `SDirection.kOut`.

The **execute** method takes care of defining the list of steps to be performed when the execution of the operator is issued inside Shift. In the example above, the execute method picks up the values of the two input plugs and multiplies them together. Finally, it stores the result in the output plug.

Please refer to the Shift API documentation to know more about which plug types are present in Shift, and which additional methods the `SPlug` and `SOperator` classes offer.
