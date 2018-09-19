########
Mycelium
########

This is the home for the architecture of Mycelium: the ecological
modelling engine I am creating.


******
Basics
******

Identifiers
===========

Identifiers use the following syntax:

global_id = model_id:node_id

model_id = model ids must be globally unique. allowed characters:
``[a-z0-9_\-.]``. uppercase are converted to lowercase.

node_id: local identifier (internal to the model). Identifiers need only be
unique within the model.

.. todo:: Identifiers can be inferred as well if there's just a list
	  of items?

Nodes have polymorphic types
============================

Each node has a type. types are polymorphic such that base types exist
and subtypes can expand on those definitions. Types can inherit from
multiple base classes.

Node types provide the following capabilities:

#. They define the data type of the node and are responsible for field
   definitions.
#. They register into the callback locations within the engine's REPL
   loop. These callbacks are used to grow and mutate the model based
   on 1) **R**eading external data 2) **E**valuating internal state, 3)
   **P**rinting out external representations of state, 4) Incrementing
   counters, flushing temporary data and **L**ooping back to read.


Nodes are split into two base classes, graphs and records
=========================================================



Formal Concept Analysis is used to define set operations
========================================================

Each node has a type. types are polymorphic. 
