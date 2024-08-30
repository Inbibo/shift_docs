# Terminology

This page assembles a list of definitions for some of Shift's main concepts.

## Workflow

A workflow is a directed acyclic graph (DAG) that builds the relationship between the execution of its nodes. A workflow is composed of interconnected nodes and defines an execution process.

## Node
Nodes are the graphic block units that build up the workflow. Each node is associated with an operator, which defines the execution logic of the node and is connected to other nodes through plugs.

## Plug

A plug represents an input or output of a node. Plugs have a type associated based their compatibility with different Python data types. Plug values can be set manually via the inspector widget or gotten from a connected plug.

## Connection

A connection is the graphical representation of two connected plugs and shows the direction of the data propagation. Connections between plugs from different nodes are what define the execution stack of the workflow. 

## Execution Stack

The execution stack refers to the order in which nodes will be executed. The execution stack is closely related to the workflow configuration, although it can be more or less extended and include repeated nodes under the presence of iterators or conditions. 

## Board

Refers to the workspace in the Shift UI where the workflow is constructed.

## Inspector

The inspector is the UI widget through which the name, inputs, and output values of a node can be inspected. It is also where values can be set manually in input nodes. 

## Operator

An operator is the scripted execution block that performs a specific process given a set of input data if required. From a programming perspective, an operator can be seen as a function that takes some input data and evaluates it to produce some output data.

## Catalog

A catalog is a collection of operators that usually share a common context.  Users can create their catalogs to organize their custom operators.

## Plugin

A plugin is a custom-based UI that can interact with Shift to display additional information, perform actions, or extend the behavior of the application.