########
Mycelium
########

This is the home for the architecture of Mycelium: the micro ecological
environment simulation/modelling engine.

The functional purpose of Mycelium is explained in :ref:`sim-engine`.


******
Basics
******

Identifiers
===========

.. TODO: Maybe this isn't as important as I initially thought. Model IDs are
   important, embedding namespacing in IDs is very useful when
   creating/referencing tree-like structures -- but this may not really be a
   core concept.

Identifiers are important to formalize because simulations are intended to be
modular. Someone should be able to easily import someone else's work to use as a
template while maintaining a link to the original source. Names need to be
referencable in a stable manner for this to work well.

Identifiers use the following syntax:

global_id = model_id:node_id

model_id = model ids must be globally unique. allowed characters:
``[a-z0-9_\-.]``. uppercase are converted to lowercase.

node_id: local identifier (internal to the model). Identifiers need only be
unique within the model.

.. TODO: Identifiers can be inferred as well if there's just a list
         of items (use indices)?

********
Language
********

Rust. Although not mature, I believe that Rust is the most compelling language
with which to make a full fledged micro-climate simulation engine.

Pros:

* A typed language, this helps when developing complicated functions that need
  to mirror reality as well as ensure data safety
* The compiler is designed from the ground up for memory safety and to enable
  multi-threaded applications. The simulations I want to perform are liable to
  be very process intensive and I want to enable these to run in local
  environments.
* Can be compiled for mac/windows/linux/android/ios. Most environments have
  this, but its good to note.
* Can be used in pretty bare bones environments -- I would like to be able to
  experiment with pieces of code in IOT devices -- specifically garden
  monitoring devices.
* Massively open source: Spearheaded by Mozilla, all code I've seen is open
  source.
* Great community, the language is well loved: https://insights.stackoverflow.com/survey/2018/#technology-most-loved-dreaded-and-wanted-languages
* Is immature: If I have the vision, I am in a place where I can influence many
  of the libraries needed to make this work.


Cons:

* Is immature: If I need something, most of the time it exists, but isn't stable
  or full-featured. There are three great tracking sites for getting a feel for
  where rust is, with respect to the types of features I will need:

  https://www.arewewebyet.org/
  http://arewegameyet.com/
  http://www.arewelearningyet.com/

* No existing models. I'll have to develop them. This is probably necessary
  regardless of what language I use anyways if I want to have a performant
  engine.



******
Engine
******

Entity Component System appears to be the best architecture for creating an
adaptable modular simulation engine.

Here's a compelling blog post on the topic:
https://hackernoon.com/ecs-vs-oop-by-example-daa712b24869

Essentially, data representation is key. My belief is that this approach will
enable quicker iteration on models, and lower the burden on adding additional
modelling capabilities. But, first and foremost I believe it will enable safer
parallelism.

I have spec'd https://github.com/slide-rs/specs as the ECS.

Higher level tools in https://www.amethyst.rs/ may also be useful.


*****************
Models to Develop
*****************

Need to be really careful here about licenses. I think I can make mycelium free
and open source with just a connection to the ecohood platform, but this needs
lawyers and stuff.

Many of the research hear is from crawling this list: https://soil-modeling.org/resources-links/model-portal

Regional Climate
================

* Just need farmers almanac type stuff I think
* Need to also apply global changes: see Asymtotic Environmentally Determined
  Trajectory https://journals.plos.org/plosbiology/article/file?id=10.1371/journal.pbio.2002634&type=printable

Water/Soil/Nutrient Movement
============================


* https://epicapex.tamu.edu/apex/
* https://github.com/MarcelVanOijen/BASFOR/tree/master/
* https://daisy.ku.dk/
* https://www.pc-progress.com/en/Default.aspx?H1D-description#k8
* https://github.com/zalf-rpm/monica/wiki
* datasets: https://soil-modeling.org/resources-links/data-portal

Soil moisture model should be pretty important. The soil should be
treated as an organism most likely, not as something inanimate.

   * https://www.rothamsted.ac.uk/models-and-analytical-tools

Microclimate
============

Continuous change, Sun angle, rain, temperature, ???. Hook into
wunderground/farmer's almanac type data if possible?

* NicheMapR – an R package for biophysical modelling https://onlinelibrary.wiley.com/doi/abs/10.1111/ecog.02360
* https://www.researchgate.net/post/What_is_the_most_practical_micro-climate_model_for_examining_the_relationship_between_urban_design_parameters_and_outdoor_thermal_comfort

Ecological databases
====================

Identify the growth characteristics of each plant by getting data a.la.
plantstuff

Plantstuff (plant DB, insect, virulence)

* https://github.com/christabor/plantstuff

Competition/Dynamic Stability, Dynamical Processes in Networks
==============================================================

* http://allison.bio.uci.edu/


Hypothesis Generation and Pipeline generation
=============================================

Objective functions optimize for things like:

* Biomass Density
* Harvest duration, mass, diversity, nutrition
* Beauty? (flowering, bird and butterfly attracting)

Estimating parameters based on data sampling
   * http://fb09-pasig.umwelt.uni-giessen.de/spotpy/

Timestep should be a day. Run for a year and output growth over time.

Need compelling data visualization here:

Main should be a yard map, with growth over time. Probably made into a gif.

Markets (economic)
==================

eek
