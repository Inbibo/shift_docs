# Terminology

Here are some of the basic terminology used in Shift:

## Operator

An operator is an execution block that is delegated of performing a specific action given a set of input data if required. From a programming perspective an operator can be seen as a function that takes some input data and processes it to produce some output data. Operators in Shift can be connected to propagate information between each other.  

*\*operator* and *node* will be used interchangeably.  

## Plug

A plug is a Shift object containing the data that is passed to or from a certain operator. An operator has input plugs on its left-side and output on its right-side.

## Workflow

A Shift workflow is a directed acyclic graph (DAG) that builds the causal relationship between the execution of its nodes.

## Catalog

A Shift catalog is a collection of Shift operators, that usually share a common context. They serve mainly for organizing the available operators. A Catalog example is [*`Shift_USD`*](https://github.com/Inbibo/Shift_USD) which contains nodes to process and manipulate Usd data or the builtin *`Workflow`* catalog which contains nodes to run nested workflows. Users can create their own catalogs to organize their custom operators.
