########################
Minimum Viable Product 1
########################


This documents the planning and actions taken while designing the
landscape our our own yard to be a research testbed for the
permacultural farm app.

.. toctree::
   :hidden:

   abstract
   mycelium
   frontend
   climate
   ecographs
   plantstuff
   simulation
   anchoring
   learning
   journal


*******
Aside 1
*******

I need some names, just so this writing isn't as awkward. Here's my
initial take.

Permanent, Farmly, Permanent Web, anthrorhiza (human root) a play on
mycorrhiza (fungus root). Maybe just human root? I'm going with
anthrorhiza for now, it may be too academic though. Maybe just Rhiza?
That's got a ring to it (a rap vibe too -- b/c of the wutang
clan). Naturehood -- mom suggested this today (9/9). Urban
Jungle. What about ecohood? I like that the best so far -- I like
naturehood but the connotation of nature has too much 'unsullied by
humans' connotation. Ecology is just the study of natural systems, so
I think it fits better. Plus you can shorten it to eHood and get the
double meaning of electronic in there.

.. glossary::

   EcoHood
      Name of the app?

   Owner
      Person with land being developed

   Operator
      Person developing/maintaining/harvesting

   Consumer
      Persons consuming the human edibles

   Property
      The owners property being modeled through EcoHood


***************
Lay of the land
***************

The first thing that needs to be input into the application is
information about the land that's being developed.

* Property Info

  * GPS coordinates marking the boundaries of the property

    * This provides information about the seasons, avg rainfall,
      sunlight etc for that area of the world

  * Input about local structures: buildings and trees
  * Input about land gradients
  * Input about soil quality

    * Readings from representative areas around the property
    * Soil Depth
    * PH, Nitrogen, Potash, Phosphorus
    * Brownland worries (lead, etc.)

* What is desired by the Owner

  * How much of the land can be developed for non-traditional lawn
    uses
  * How beautiful should it be?
  * How much initial investment in the land is available
  * How much yearly investment is available (for operations,
    resource upkeep, and processing)
  * How long are they expected to own the property. How long term can
    the investment be?
  * What is the desired output of investment? Food, beauty, smaller
    land operations costs, cashflow

* What is desired by the Operator

  * What is the level of skill and knowledge of planting and growing
  * How much time is available
  * Are there seasonal/hour restrictions? How robust is operations to
    small big crunchtimes vs continuous even work?

* What is desired by the Consumer

  * How adventurous is the consumer with new species/tastes?
  * Are there markets that will buy the small amounts of product
    expected from a single property?

:doc:`abstract`


*************************
Step 0: Simulation Engine
*************************

I really don't know if its a good idea or not, but I'm very inclined
to use what I learned from tracegraph at SpaceX to create an
underlying engine. I think I'll call it Mycelium

.. glossary::

   Mycelium
      Mycelium provide a useful analogy to what the purpose of the
      data base is for: It breaks down complicated systems and
      provides a linkage in order to connect them. This break down and
      linkage is then used to increase their 'nutrition' by providing
      knowledge on how they could work better. It is intended to work
      out of sight, but be a keystone species for the success of the
      ecosystem, in this case the :term:`EcoHood` app.

      The following are some excerpts from the `mycelium wikipedia page`_:

          Mycelium is the vegetative part of a fungus or fungus-like
          bacterial colony, consisting of a mass of branching, thread-like
          hyphae.

          Mycelium is vital in terrestrial and aquatic ecosystems for
          their role in the decomposition of plant material. They
          contribute to the organic fraction of soil, and their growth
          releases carbon dioxide back into the atmosphere (see carbon
          cycle). Ectomycorrhizal extramatrical mycelium, as well as the
          mycelium of Arbuscular mycorrhizal fungi increase the efficiency
          of water and nutrient absorption of most plants and confers
          resistance to some plant pathogens. Mycelium is an important
          food source

          Mycelium", like "fungus", can be considered a mass noun, a word
          that can be either singular or plural. The term "mycelia",
          though, like "fungi", is often used as the preferred plural
          form.


.. _mycelium wikipedia page: https://en.wikipedia.org/wiki/Mycelium

This is because the lessons I learned through that effort are well
suited here due to:

* polymorphic types match closely to plant families
* Node and graph based computation triggers
* Log and attribute recording over simulations

In order to do this, I need to recreate the code using just my mental
understanding of what I accomplished. Create tests along the way, and
move it into an architecture that makes it friendly to parallel
computation.

The source attribution concept may be useful, I'm not sure though.

:doc:`mycelium`

*********************
Step 1: Render a yard
*********************

Need to input coordinates and types of initial plantings. Also need to
input physical objects, and the topology of the space.

:doc:`frontend`

******************************
Step 2: Create a climate model
******************************

Continuous change, Sun angle, rain, temperature, ???. Hook into
wunderground/farmer's almanac type data if possible?

:doc:`climate`

*********************************
Step 3: Add minimal object models
*********************************

Shade, water, nutrient, growth, and decay models to
rendered objects. Birds, Insects, operators.

Soil moisture model should be pretty important. The soil should be
treated as an organism most likely, not as something inanimate.

:doc:`ecographs`

***********************************
Step 4: Hook into species databases
***********************************

Identify the growth characteristics of each plant by getting data a.la.
plantstuff

:doc:`plantstuff`

***************************
Step 5: Propagate the model
***************************

Timestep should be a day. Run for a year and output growth over time.

Need compelling data visualization here:

Main should be a yard map, with growth over time. Probably made into a gif.

:doc:`simulation`

******************************
Step 6: Anchor the propagation
******************************

Each model should have a test dataset and expected result integrated
with it.

Later the yard becomes an integrated test dataset as well: record the
initial conditions and growth and shade and temp metrics over the
year.

   This will be difficult: How should this data be aggregated? that's
   a project unto itself.

   Webcams with temp and moisture sensors may be sufficient
   actually. Then take soil readings every couple months?

   Haven, by gaurdian project is an open source project to turn old
   phones into a security cam. This seems promising to use as the
   basis of a time lapse camera for plant monitoring. The updates
   would be: make a solar powered, water proof enclosure, add a
   thermometer to the enclosure and hook it to the phone. Maybe add a
   wifi extender to the house to allow pushes to the main pc as the
   principle data repo.

   I have until the spring to get this set up. eek!

:doc:`anchoring`

**********************************************************************
Step 7: Provide an objective function and start genetic algorithm runs
**********************************************************************

Objective functions optimize for things like:

* Biomass Density
* Harvest duration, mass, diversity, nutrition
* Beauty? (flowering, bird and butterfly attracting)

:doc:`learning`

**********************************************
Stepping Back: Tacktics, Focus, and Motivation
**********************************************

In order to use and evaluate this software as a product, I'm going to
have to take shortcuts this winter and make a lot of tactical and
strategic decisions. I'll keep a journal of this process.


:doc:`journal`
