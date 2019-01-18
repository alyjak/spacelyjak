Responses below!

----------------

 Hi Andrew,

Yes, some interesting thoughts here, I am a bit behind the curve when it comes to technology
usage. I only use my iPhone rarely, as I don't like the small screen, but apparently I am in the
minority, according to my friends.  So you might well be right in that it might be better to release
it as a phone app.

> Actually what I'm trying to do is release it as a cross-platform app using web technologies. Ionic
  allows me to create an app that can be used in the browser, on a PC via Element (similar to software like the
  Spotify app, or Gitter to name two examples), or for Android or iphone as well.

To be honest, once I have made a bit more progress on the back end (I have spent most of my time so
far doing research) I will share it with you, and you can see what you think. I don't really have
any strong ideas about how it is eventually presented to the user, so I am happy to go with the flow
on this one.

> cool! Let me know if you need a sounding board for any of your design decisions or need any help
  programming. I have experience with Python, Matlab, C, C++, Rust, and web technologies (html, css,
  js, etc.), as well as a mathematical background (Aerospace engineering degree).

Having said that, I might have to respectfully disagree that the audience will be small. A lot of
folks I have talked to about this have thought that it would be a good idea, and a $10 - $20 program
won't break the budget.

> That's good to know, but be careful forming business decisions just based on testimony by people
  you know. Also, forming a fully formed game that can be sold for that price point may be too big a
  risk for me to help with. The benefits of something that can be put on an app store are that
  incremental improvements can be released, which lowers time to market. Also it allows the features
  to be adapted based on gathering information on what people like and don't like in the early
  versions of the game/simulation/app, rather than just guessing.

I am aiming this more towards the people who are interested in permaculture, but don't have the
time, energy, land or money to devote to exploring it. Not sure about the US, but in NZ, there are
tons of people who like the idea of going off grid, but can't for whatever reason.

> I don't see the game aspect as divergent from what I've described actually. I'm going try and put
  together some user stories today, but the way I see it if you focus on providing an app that
  allows you to plan and helps you maintain your property, that same experience can be applied to
  the property you wish or imagined you have. So basically there's two ways to 'play' you can play
  just in in app, or you can have what's essentially an augmented reality experience -- where you
  use your 'play' in the app to influence your 'play' in the real world.

The thing about a "game" vs a "simulation" thing is that a game might be more approachable/ marketable.

> So I see the simulation as an engine. An engine usually isn't a product unto itself, it just
  powers the product. What needs to occur is finding a product that garners enough interest to allow
  continuous development and improvement of the the simulation engine. Also, there's many products
  this engine can be integrated in. For example, I think you ran into this as well -- there seems to
  be a lack of wholistic ecological modeling software available. I know that when I was researching
  this, I was pretty disappointed by what I could find. Here's a list of the most promising things I
  came across:

  Many of the research here is from crawling this list: https://soil-modeling.org/resources-links/model-portal

  * Regional Climate

    * Just need farmers almanac type stuff I think
    * Need to also apply global changes: see Asymtotic Environmentally Determined
      Trajectory https://journals.plos.org/plosbiology/article/file?id=10.1371/journal.pbio.2002634&type=printable

  * Water/Soil/Nutrient Movement

    * https://epicapex.tamu.edu/apex/
    * https://github.com/MarcelVanOijen/BASFOR/tree/master/
    * https://daisy.ku.dk/
    * https://www.pc-progress.com/en/Default.aspx?H1D-description#k8
    * https://github.com/zalf-rpm/monica/wiki
    * datasets: https://soil-modeling.org/resources-links/data-portal

  * Soil moisture model should be pretty important. The soil should be treated as an organism most
    likely, not as something inanimate.

     * https://www.rothamsted.ac.uk/models-and-analytical-tools

  * Microclimate

    * NicheMapR – an R package for biophysical modelling https://onlinelibrary.wiley.com/doi/abs/10.1111/ecog.02360
    * https://www.researchgate.net/post/What_is_the_most_practical_micro-climate_model_for_examining_the_relationship_between_urban_design_parameters_and_outdoor_thermal_comfort

  * Ecological databases

    Many of these are pulled from an integrated plant database a friend of mine is developing:
    https://github.com/christabor/plantstuff. Others are pulled from the Resources section of Gaia's
    Garden, second edition by Toby Hemenway

    * Dr Duke's Phytochemical and Ethnobotanical Databases: https://phytochem.nal.usda.gov/phytochem/search
    * Plants for a future https://pfaf.org/user/Default.aspx
    * USDA Plants Database https://plants.usda.gov/java/factSheet
    * Dave's garden plant files: https://davesgarden.com/guides/pf/
    * Monrovia Plant Catalog: https://www.monrovia.com/plant-catalog/
    * Perrenials plant catalog: http://www.perennials.com/results_alphabet.html?letter=A
    * Spring Hill Nursery Plant Finder: https://www.springhillnursery.com/category/plant_finder
    * UConn plant database: http://hort.uconn.edu/
    * wikipedia: https://en.wikipedia.org/wiki/Category:Lists_of_plant_species

  * Competition/Dynamic Stability, Dynamical Processes in Networks

    * http://allison.bio.uci.edu/

Accuracy need not be compromised just because it is a game. (Maybe also see my response to Bernetta
on this post:
https://permies.com/t/100306/permaculture-projects/Front-Programmer-Permaculture-Game-Required#827142)

> Agreed, but its hard to rationalize the additional verification and development work for an
  application that doesn't _need_ to be accurate.

I would agree also that Permaculture really needs some good data and science behind it. (That said,
the concepts are sound and proven, but we can't easily quantify the effects of certain measures) So
I would agree that a good simulation would help facilitate that.

> Agreed that the principles are sound, but even on the permies.com forum, there's quite a few
  complaints on how many testimonials, rather than quantitative improvements are
  recorded.

  * https://permies.com/t/16557/permaculture
  * https://permies.com/t/99768/ways-money-homestead


My questions regarding what you have said:

Are you sure that a mobile device would have enough processing power to simulate the natural
systems? Or would you send the input off to a server to run the calculations (Unless I am mistaking
the complexity you mean to embed in the software)

> I'm not concerned about processing power for a couple of reasons:

  #. Each run of the simulation may be processing intensive, but it doesn't need to run at real time
     like a first person video game for example. The processing just needs to occur whenever the
     user makes a change.
  #. Many of the simulation results can be pre-calculated. For many things this doesn't even need a
     cloud server. Similar to machine learning, many of the calculations may be intensive to
     calculate at first, but then using their results is not intensive, and their results can be
     used many times over.

I think that there are a few apps already out there that offer generic gardening advice. Do you
think that you will be able to differentiate the app you are making from those others?

* True, I have collected a few lists of them but I wasn't satisfied with them. Most of the apps just
    wrap around an existing plant database and essentially offer you bookmarks to those database
    pages. Either that or they are glorified note taking apps that you can keep lists of your plants
    on. A couple features that I want:

  - I want the app itself to offer recommendations on what I should plant, where i should plant it,
    and why.
  - I want the app to pre-schedule checkups, recommend I take pictures and measurements, and also
    help me if with recommendations if the planting isn't healthy.
  - This is a later feature that I want to develop once the app is stable: I want the app to provide
    a messaging and market place such that I can work with my neighbors to share resources,
    harvests, and other activities.

Also, once you have a working backend, which could run through the calculations, it would seem a
shame to limit it only to back lawns. I was thinking you might as well go whole hog, and let it be
used by people who want to design entire sections.

> Agreed, there's no need to artificially restrict usage like this. I was principally referring who
  I would like to market the product to. See my comment on the game above

As I think about it, 2-D might be the way to go. But I am curious as to how you plan to addess the
above. Maybe we can end up helping each other in some way,

> I hope my responses helped clarify my positiion! Thanks for talking with me!

Cheers,

Henry
