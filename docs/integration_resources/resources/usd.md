# USD

Shift has developed a specialized catalog and utility plugins for using the USD API in Shift. 

* [Shift_USD](https://github.com/Inbibo/Shift_USD)

## Installation

To start working with the USD API in Shift, please follow the following steps:

* Download the necessary dependencies (Python & USD).
* Clone the [Shift_USD](https://github.com/Inbibo/Shift_USD) repository into the preferred folder.
* Add the path to the Shift_USD directory to the `PYTHONPATH` environment variable.
* Add the path to the Shift_USD directory to the `SHIFT_CATALOG_PATH` environment variable.
* Add the path of the *plugin.json* file found in the Shift_USD directory to the `SHIFT_PLUGIN_PATH` environment variable.

## Dependencies
| **Dependency**                                           | **Version**    |
| -------------------------------------------------------- | -------------- |
| [Python](https://www.python.org/download/releases/3.0/)  | 3.7 or higher  |
| [USD](https://pypi.org/project/usd-core/)                | 21.8 or higher |

<!-- ##Plugins

TODO #43
This section is reserved to USD Plugins information 

### Examples
This section is reserved to an example video of how to use USD resources.
 -->

## Tutorials

To start learning how to use the different operators implemented for the Shift_USD catalog, a series of tutorials are helpful to understand the overall of the basic operators. These following tutorials are inspired on the Pixar's tutorials from the [OpenUsd](https://openusd.org/release/tut_usd_tutorials.html) project webpage:

1. [Creating Your First USD Stage](usd_tutorials/usd_tutorial_01.md)
2. Inspecting and Authoring Properties
3. Referencing Layers
4. Converting Between Layer Formats
5. Traversing a Stage
6. Authoring Variants