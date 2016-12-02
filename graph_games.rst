###########
Graph Games
###########

A complicated, multi-level graph "game" loosely inspired by Conway's game of
life.

This document tries to procedurally define the rules and setup for graph
games. The document concludes with musings on interesting things that may be
simulated using this game.

.. contents::

*********
Objective
*********

The objective is to construct a multi-layer network network that shows some
interesting time variant behavior when run through a simulation subject to the
following definitions. This document lays out 1) how to run the simulation, 2)
what the simulations could be used for, 3) the data definitions for the
structures within the multi layer network.

*************************
How The Simulation Is Run
*************************

An initial network setup seeds the game. See the last section for how the network
setup is defined.

The simulation consists of a state machine that executes until terminated by a
user. Each simulation step is composed of the following sequence of events.

#. Node Type functions are run on each node of that type, the node type function
   evaluates whether the node is alive or dead, and whether to create a new node
   or not. The type function operates off of any data value stored within a
   node, as well as off of the set of edges immediately connected to the node.
#. Dead nodes are removed from the graph. Removing a node removes all edges that
   node is a part of
#. Graph functions are run on each graph in the multi layer network. Graph
   functions can: add, remove, or modify edges within the graph, or modify the
   values of nodes connected within the edges of the graph.

These steps result in a new network setup, which is then fed in as the input for
the next simulation cycle.


******************
Network Definition
******************

Given a multi-layer network of the following form

.. math::
   :label: MLN

   MLN = (V, U)

Where U is a set of graphs :math:`U = {G_1, ... , G_h}`. And V is a set nodes,
such that edges in each graph within :math:`U` must be constructed of vertices
only from nodes within :math:`V`.


****************
Node Definitions
****************

Given an array of globally unique nodes :math:`V = {v_1, v_2, .. , v_v}`, where
each node, :math:`v_v` is a tuple of the form:

.. math::
   :label: node_definition

   v_v = (k_v, T_i, d_v, a_v)

Where the node tuple contents are as follows:

   :math:`k_v`
      A string that uniquely names node :math:`v_v`, such that we can use
      :math:`k_v` to map to the node tuple.

   :math:`T_i`
      A reference to the node type tuple :math:`T_i`

   :math:`d_i`
      A tuple of values, where the number of values and the type of each value is
      determined by :math:`D_i`, which is defined as part of the node type tuple
      :math:`T_i`.

   :math:`a_v`
      A boolean value representing if :math:`v_v` is alive or dead. Each node is
      initially set to alive (True), and if a_v is changed to dead (False). In most
      variants of the game, :math:`v_v` is removed from :math:`V` once :math:`a_v =
      False`

:math:`T_i` is part of the set of node types, :math:`T = {T_1, ... , T_v}`. Each
node type is a tuple of the following form:

.. math::
   :label: node_type_definition

   T_i = (k_i, D_i, NF_i)

Where the node type tuple contents are as follows:

   :math:`k_i`
      A string that uniquely names node :math:`T_i`, such that we can use
      :math:`k_i` to map to the node tuple.

   :math:`D_i`
      A tuple definition, that defines the data variables, and the data types for
      nodes of this node type

   :math:`NF_i`
      A function that returns whether a node :math:`v_v` is alive or dead, given
      the values of the node's data. Additionally, the function may create an
      new node :math:`v_{v + 1}` or not, such that :math:`V` is either unchanged
      or increased in size by one.

      .. math::
         :label: node_aliveness_function

         NF_i(d_v) = a_v, V

*****************
Graph Definitions
*****************

Each Graph is a tuple containing the graph itself, and a graph function
associated with the graph type.

.. math::
   :label: graph_tuple_definition

   G_h = {k_h, E_h, GF_h}

Where the graph tuple contents are as follows:

:math:`k_h`
   A string that uniquely names graph :math:`G_h`, such that we can use
   :math:`k_h` to map to the node tuple.

:math:`E_h`

   The set of edges for graph :math:`G_h`, :math:`E_h = {e_{h_1}, ... , e_{h_z}}`
   where each edge in the set is of the form:

   .. math::
      :label: edge_definition

      e_{h_z} = (k_{v_a}, k_{v_b}, attr)

   Where :math:`k_{v_a}, k_{v_b}` are valid node keys and :math:`attr` is a set of
   edge attributes.

:math:`GF_h`

   The graph function add, removes, and/or modifies the edges within :math:`E_h`
   based on the values :math:`V`, and :math:`E_h` such that:

   .. math::
      :label: graph_function_definition

      GF_h(V, E_h) = E_h

