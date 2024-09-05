# standard
A catalog to work with standard Python operations. It provides logic to perform loop iterations and create scriptable Python nodes. It also includes operators to read/write JSON files, operate with lists, strings, dictionaries and more.

## *standard* Operators
## Iterator
<figure style="width: 30%">
	<img src="images\iterator.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Implements a for loop in Shift.
    This works by generating multiple execution stack, each using a value from a list as inputs.
    Each execution stack uses one value from the list as if it was effectively iterating over the input values list.
    Outputs the iterated value from the input list.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| inValues | List | []

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| outValue | Object | None


## IteratorEnd
<figure style="width: 30%">
	<img src="images\iteratorend.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Defined the end of a for loop in Shift.
    This specific node is found by the graph evaluator to stop the iterative expansion fo the graph.
    This operator accepts an extensible list of plugs (through) to copy the result of the iterator.

    

## ConditionEquals
<span style="color: yellow"><i>Beta operator</i></span>
<figure style="width: 30%">
	<img src="images\conditionequals.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Compares two input objects.
    The result of the comparison is used to branch the execution stack.
    Outputs two Boolean values, one (truePlug) set to True if the two values are equal and another (falsePlug) set to True if the two values are different.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| value1 | Object | None
| value2 | Object | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| true | Bool | False
| false | Bool | False


## List
<figure style="width: 30%">
	<img src="images\list.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


This operator implements a list of Python objects.
    The operator does not have any input.
    To modify the content of the list other operators are used.
    Outputs and empty list.

    

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| list | List | []


## ListAppend
<figure style="width: 30%">
	<img src="images\listappend.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Operator to append an element to a List.
    The elements to be added are defined by user-defined input plugs added to the operator.
    Outputs the resulting list as a new list instance (does not alter the input list).

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| inList | List | []

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| outList | List | []


## ListExtend
<figure style="width: 30%">
	<img src="images\listextend.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Extends an input list adding another list to it.
    It allows selecting whether the input list is mutated or is left immutable.
    Outputs the list resulting from the addition of the two input lists.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| inList | List | []
| copy | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| outList | List | []


## ListGet
<figure style="width: 30%">
	<img src="images\listget.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Retrieves the list's element at a given index.
    Outputs the Python object at the given index in the list.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| list | List | []
| index | Int | 0

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| outValue | Object | None


## ListAccumulator
<figure style="width: 30%">
	<img src="images\listaccumulator.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Operator to accumulate an element to a List (based on ListAppend but using kInstance).
    The elements to be added are defined by user-defined input plugs added to the operator.
    Outputs the list instance (equal to the input list).

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| inList | Instance | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| outList | List | []


## ListSort
<figure style="width: 30%">
	<img src="images\listsort.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Sorts the items in the given list. 
    Optionally one can turn on the reverse option to get the list sorted in reversed.
    Outputs the sorted list.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| inList | List | []
| reverse | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| outList | List | []


## ListLength
<figure style="width: 30%">
	<img src="images\listlength.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Gets the length of the provided list.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| inList | List | []

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| length | Int | 0


## ListPop
<figure style="width: 30%">
	<img src="images\listpop.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Pops the item placed in the provided index from the provided list.
    Outputs the list updated and the item.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| inList | List | []
| index | Int | 0

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| outList | List | []
| item | Object | None


## ListReverse
<figure style="width: 30%">
	<img src="images\listreverse.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Reverse the items of a list and output the reversed list.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| inList | List | []

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| outList | List | []


## ListInsert
<figure style="width: 30%">
	<img src="images\listinsert.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Operator that inserts an item into the given list at the given index.
    Outputs the updated list.
    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| inList | List | []
| item | Object | None
| index | Int | 0
| outList | List | []

## ListRemove
<figure style="width: 30%">
	<img src="images\listremove.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Removes an item from the provided list.
    Optionally one can choose to remove the provided item recursively if there is more than 1 occurrence in the list.
    Outputs the list with the item removed.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| inList | List | []
| item | Object | None
| removeDuplicates | Bool | False

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| outList | List | []


## Print
<figure style="width: 30%">
	<img src="images\print.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Operator for printing out messages.
    Outputs the same message that was printed.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| text | String | ""
| label | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| output | String | ""


## PythonScript
<figure style="width: 30%">
	<img src="images\pythonscript.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Executes a scripted Python code.
    The node accepts any custom object as input.
    Outputs the result of the script if the 'output' variable is explicitly set in the code.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| script | Code | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| output | Object | None


## Dict
<figure style="width: 30%">
	<img src="images\dict.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


This operator implements a dict object in Python.
    The operator does not have any input.
    To modify the content of the dict other operators are used.
    Outputs an empty dict.

    

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| dict | Dict | {}


## DictSet
<figure style="width: 30%">
	<img src="images\dictset.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Sets dictionary values by keys defined by the user as input plugs.
    The name of the plug relates to the name of the key to be set.
    Outputs the dictionary after the new values are set.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| dict | Dict | {}

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| dict | Dict | {}


## DictSetKey
<figure style="width: 30%">
	<img src="images\dictsetkey.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Sets dictionary value of a key defined by the user.
    Outputs the dictionary after the new value is set to the provided key.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| dict | Dict | {}
| key | String | ""
| value | Object | None

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| dict | Dict | {}


## DictGet
<figure style="width: 30%">
	<img src="images\dictget.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Get values from dictionary given a series of user-defined output plugs as keys.
    Outputs the value assigned to the specified key (output plug) from the dictionary.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| dict | Dict | {}

## DictKeys
<figure style="width: 30%">
	<img src="images\dictkeys.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Retrieves the list of keys from a dictionary
    Outputs the list of dictionary's keys.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| dict | Dict | {}

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| keys | List | []


## JsonWrite
<figure style="width: 30%">
	<img src="images\jsonwrite.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Writes a Python Dictionary to a JSON file.
    Optionally one can select the encoding for the write mode. By default it is utf-8.
    Optionally one can also select the createFile option, if the file does not exist this will create it. Otherwise it will raise an error.
    The write mode can be selected between Overwrite or Extend.
    Outputs the filepath for the JSON file.

    

#### Inputs
| Name | Type | Default | Options
| --- | --- | --- | --- |
| data | Dict | {} | 
| filepath | FileIn |  | 
| encoding | String | "utf-8" | 
| createFile | Bool | True | 
| writeMode | Enum | Overwrite | Overwrite, Extend

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| filepath | String | ""


## JsonRead
<figure style="width: 30%">
	<img src="images\jsonread.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Reads data from a JSON file. Optionally one can define its encoding, by default is utf-8.
    Outputs the read data.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| filepath | FileIn | 
| encoding | String | "utf-8"

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| data | Dict | {}


## JsonWriteString
<figure style="width: 30%">
	<img src="images\jsonwritestring.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Reads data from a Python Dictionary and serializes it to a JSON string.
    Outputs the converted data.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| data | Dict | {}

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| jsonString | String | ""


## JsonStringRead
<figure style="width: 30%">
	<img src="images\jsonstringread.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Reads data from a JSON string and deserializes it to a Python object.
    Outputs the Python object.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| string | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| content | Object | None


## StringFormat
<figure style="width: 30%">
	<img src="images\stringformat.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Formats the given template string by using the arguments provided.
    Two types of arguments can be specified, positional (list) or named (dict).
    Outputs the formatted string.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| templateString | String | ""
| positionalArgs | List | []
| namedArgs | Dict | {}

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| outString | String | ""


## StringSplit
<figure style="width: 30%">
	<img src="images\stringsplit.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Operator that splits the given string into substrings.
    One can select the delimiter to the substrings, by default the delimiter is a whitespace.
    One can also select the maximum splits to be applied, by default the value is -1 which means unlimited splits.
    Ouputs a list containing all the substrings.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| string | String | ""
| delimiter | String | ""
| maxSplits | Int | -1

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| substrings | List | []


## StringConcatenate
<figure style="width: 30%">
	<img src="images\stringconcatenate.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Operator to concatenate the provided strings.
    The operator provides the user with two standard string plugs to concatenate.
    If the operator needs to concatenate more than 2 strings, custom string plugs can be added as needed.
    Optionally the resulting string can have a separator between each provided string. By default it is an emtpy string.
    Outputs the resulting string.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| string1 | String | ""
| string2 | String | ""
| separator | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| outString | String | ""


## StringLength
<figure style="width: 30%">
	<img src="images\stringlength.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Returns the length of the string passed in.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| string | String | ""

#### Outputs
| Name | Type | Default |
| --- | --- | --- |
| length | Int | 0


## Sleep
<figure style="width: 30%">
	<img src="images\sleep.png" alt="Node UI">
	<figcaption>Node UI</figcaption>
</figure>


Operator that puts the current thread execution to sleep for a given number of seconds.

    

#### Inputs
| Name | Type | Default
| --- | --- | --- |
| seconds | Float | 0.0

