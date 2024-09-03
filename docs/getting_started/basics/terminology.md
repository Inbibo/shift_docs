# Terminology

This page assembles a list of definitions for some of Shift's main concepts.

## Workflow

A workflow is a directed acyclic graph (DAG) that builds the casual relationship between the execution of its nodes. A workflow is composed of interconnected nodes and defines the global execution logic of the automation process.

## Node

Nodes are the graphic block units that build up the workflow. Each node is associated with an operator, which defines the execution logic of the node and is connected to other nodes through plugs.

## Plug

A plug represents an input or output of a node. Plugs have associated types based on the Python object that they should contain. Plug values can be set manually via the inspector widget or propagated from a connected plug.

## Connection

A connection is the graphical representation of the relationship between two plugs and shows the direction of the data propagation. Connections between plugs from different nodes are what defines the execution stack of the workflow. 

## Execution Stack

The execution stack refers to the order in which nodes will be executed. The execution stack is closely related to the workflow configuration. It can be a linear execution list of nodes in the workflow or dynamically expand or contract under the presence of iterators or conditionals. 

## Board

The board refers to the workspace in the Shift UI where the graphical counterpart of the workflow is build. It is the master object holding all information on the graphic items in the interface.

## Inspector

The inspector is the UI widget through which the name, inputs, and output values of a node can be inspected or manually modified.

## Operator

An operator is the logical counterpart of a node and performs a specific process given a set of input data, if required. From a programming perspective, an operator can be seen as a function that takes some input data and evaluates it to produce some output data.

## Catalog

A catalog is a collection of operators that usually share a common context.  Users can create their own catalogs to integrate their custom operators into Shift.

## Plugin

A plugin is a custom-based UI that can interact with Shift to display additional information, perform actions, or extend the behavior of the application.
