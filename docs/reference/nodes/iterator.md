# Iteration Nodes

Iteration Nodes are used to create and define loops within a workflow. 

## Iterator Node

This node forces the execution of the subgraph composed by the nodes following the *Iterator* node as many times as the number of elements passed to the input of the node. Each execution of the loop uses one value from the input iterable object as if it was effectively iterating over its elements.

<figure style="width:80%;" markdown>
    <img src="images/iterator.png" alt="Iterator UI">
    <figcaption><b>Figure 1</b>: Iterator Node UI.</figcaption>
</figure>

>[!NOTE]
> *Iterator* Nodes can be nested, meaning that another *Iterator* node can be placed inside the loop of an *Iterator* node to achieve multiple levels of iteration.

### Inputs

- **inValues** : This plug of type [Instance](nodes#plugs) expects an iterable Python object, such as lists, dictionaries, sets or tuples. The number of elements of the iterable object will determine the number of loops the *Iterator* node will execute.

### Outputs

- **outValue**: This plug of type [Instance](nodes#plugs) will output one value of the input iterable object corresponding to the current iteration. This means that the output of this plug will change dynamically for each loop the iteration Node executes. 


## IteratorEnd Node
The *IteratorEnd* node is used to define the end of a loop started by an *Iterator* node. This means that only the nodes between the *Iterator* and the *IteratorEnd* will compose the subgraph used for the execution loop. It is recommended to always have one *IteratorEnd* node per *Iterator* node in a workflow.

<figure style="width:80%;" markdown>
    <img src="images/iteratorEnd.png" alt="IteratorEnd Node">
    <figcaption><b>Figure 2</b>: IteratorEnd Node UI.</figcaption>
</figure>

>[!NOTE]
> It is advised to connect to the *IteratorEnd* node the output generated in the loop via a custom `through` plug. The output plugs of the *IteratorEnd* node will contain the the values of the last iteration. 

## ListAccumulator Node
The *ListAccumulator* node allows to accumulate the result of each iteration of the loop. The elements to be appended to the list are defined by custom input plugs added to the node.

<figure style="width:80%;" markdown>
    <img src="images/listAccumulator.png" alt="ListAccumulator Node">
    <figcaption><b>Figure 3</b>: ListAccumulator Node UI.</figcaption>
</figure>

### Inputs

- **inList**: This plug of type [Instance](nodes#plugs) expects the list where the values will be accumulated into.

Custom plugs should be added to the *ListAccumulator* plug to define which elements should be accumulated in the list. There is no limit of custom input plugs that can be added. The elements will be appended in the same order they were created in the node. 

>[!NOTE]
> It is highly recommended to use the *ListAccumulator* node in conjunction of a *List* node that provides an empty list. The output plug of the *List* node should be connected to the *inList* input plug from the *ListAccumulator*. This way, the *ListAccumulator* will properly be reset when the workflow graph is cleared.  

### Outputs

- **outList**: This plug of type [List](nodes#plugs) will output a copy of the list with the new appended values.

<!-- ### Examples
TODO: #62
This section is reserved to an example video of how to use the Iterators nodes.

 -->