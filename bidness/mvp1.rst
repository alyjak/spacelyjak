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

.. _sim-engine:

*************************
Step 0: Simulation Engine
*************************

A simulation engine is necessary in order to guide and work with users in order
to inform their decisions by providing them 1) with data on their current
micro-environment, 2) providing them with possibilities on what the
micro-envronment could become, and 3) guidance on what immediate steps need to
be taken to achieve a desired micro-environment. The simulation engine becomes
the universal Permaculture guru who's accessible to everyone, and becomes
smarter and better because of everyone it interacts with.

.. glossary::

   Mycelium
      The name of the ecoHood micro-environment simulator. Mycelium provide a
      useful analogy to what the purpose of simulator is for: It breaks down
      complicated systems and provides a linkage in order to connect them. It
      funnels resources (in this case information) to those in need. It
      decomposes the complicated environment into digestible pieces. This break
      down and linkage is then used to increase owner and operator's 'nutrition'
      by providing knowledge on how they could work better. It is intended to
      work out of sight, but be a keystone species for the success of the
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

:doc:`mycelium`

****************************
Step 1: Capturing local data
****************************

Having an engine for performing simulations is only useful when such simulations
affect the user. The interaction must feel tangible and personal. Also, the
higher the fidelity of local data inputs, the greater the chance of producing
useful outputs for the user -- even in the face of limited, incomplete modeling
capabilities.

First and foremost, the necessary data is an accurate layout of the location
(latitude, longitude), plus micro map of the space (walls, slopes, existing
plants, etc.). Ideally entering such data is a 5 minute or less exercise for the
user, and also can be validated somehow.

In addition to structural mapping, the other data entry is feedback on how the
plants are doing. Getting snapshots over time of a planned and executed garden
allows interventions, and also allows better training of the models.

As what I'm asking for is a map with categorized elements, a naive approach here
would not be tractable. I can't assume every person can create a good map of
their location. Here are some possibile solutions:

* Use a market where people can be hired to 'survey' the space

  Pros:
     data quality should be good

  Cons:
     Drastically increases cost of entry into the ecohood. Recurring cost to
     keep up to date. Also dependent on training/accessing this type of
     expert. Still doesn't remove the need to create a data entry protocol and
     validation pipeline.

* Parse google maps and other satellite data

  Pros:
     Immediately available, quick and easy for the user

  Cons:
     Requires image segmentation, variable quality, low resolution, beholden to
     external APIs. Height and small plant data aggregation is especially
     limited.

* Machine learning to parse a user's video into a 3D representation

  Pros:
     Quick and easy for the user, data can be re-acquired anytime the user has a
     moment to walk around their yard. Any gaps can be iteratively corrected by
     interacting with the user. Works as a stand alone product that has other
     capitalizations (house design, house inventory, iot sensor mapping,
     augmented reality)

  Cons:
     Not mature technology, no existing product here. At state of the art for
     computer vision technology.


I am going to try machine learning to start, because that is the most promising.

I'll call the application :term:`surveyor` for now.

.. glossary::

   Surveyor
      The application for transforming video into a segmented model of a user's
      property.

:doc:`surveyor`


*******************************************
Marketing, network growth, and monetization
*******************************************

As Tim Ferriss says, need 1000 die hard fans.




*******************************************
Step 6: Learning, Anchoring, and Validation
*******************************************

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

**********************************************
Stepping Back: Tactics, Focus, and Motivation
**********************************************

In order to use and evaluate this software as a product, I'm going to
have to take shortcuts this winter and make a lot of tactical and
strategic decisions. I'll keep a journal of this process.


:doc:`journal`
