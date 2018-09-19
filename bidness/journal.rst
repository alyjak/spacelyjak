***********************************
Garden Planning/Modeling Brainstorm
***********************************

2018-09-07 (guessed on 9/15)

Should start with macro pieces that are well known pieces: Keyhole,
espalier, swale, spiral, hugelkultur, high yield techniques (1 sq ft
pieces of raised beds).

Should maybe also focus on neighborhood gains first -- sharing economy
and community building. Can this be integrated into an existing app?
NextDoor? Craigslist?

The modeling would be inspired by AEDT, be a generative model that
predicts relative sizes of a crop over time based on calculations of
microclimates and resources.

 * need fuzzy and hard collision detection
 * each crop can just be represented as stacked geometric shapes with
   spring constants for collision. This may work for modeling the
   give and take that closely planted plants perform. When the spring
   force becomes too great, the plants growth coefficient is greatly
   minimized.

Initial model would have all inputs specified, then could have a
genetic algorithm (or something of the likes) which modifies the
inputs (in terms of species and placement) in order to try and
optimize output factors.


***************************************************************************
How to do enough to "use" this and get the yard planted before Spring 2019?
***************************************************************************

2018-09-10 (Guessed on 9/15)

I can't do everything at once! The
following is a brainstorm of the planning and ordering I should do:

1. Choose plants

   Focus on starting zone 1 and controlling the edges.

2. Chose a rough layout. Don't plan on doing it all at once though

   This probably means that my dreamed up natural pond won't happen in
   the next year. I need to make sure I can still start the trees I
   want in the meantime:

   1. Chestnuts will start in pots
   2. Sequoia needs another year or more in a pot
   3. Bamboo will be on the outskirts somewhere
   4. can add some fruit trees to the front yard. What about a red oak
      guild? hazel, paw paw, horseradish
   5. I also want to actively incorporate fungi from the get
      go. Definitely some edible species, but more importantly explore
      mycorrhizal types

3. Hire a permaculture expert to review plans


****************************************
Getting Some Code: What language to use?
****************************************

2018-09-15

Tradestudy:

I need to be quick, but I also need to set myself up for stability,
ability to refactor, code performance (I want simulations to be able
to be run on personal computers), and ability to run on large and
small machines (small software on outside sensors, code on
smartphones, code on pcs, code on servers). Also, Rust has a strong
type system and some pretty strong functional elements. I have hope
that those will serve me well.

Right now I'm thinking that Rust balances these needs quite well.

My worries are mainly:

1. the immaturity of the language (its used in big production systems
   now though -- Firefox Quantum)
1. My ability to be comfortable with the language
1. The quality and variety of the available libraries


Today, and this weekend in general, I'm going to investigate using
Rust. My objectives are to:

1. Get a hello world server running. Hook in a graphql query and response
1. Get a unit test for loading and saving a yaml file
1. Start making the strangedb and the modelinterface

Evaluate how it went on Monday evening. Talk to Brandy or Adrian about
how it went. If it seems promising, run with it. If not, look at other
options:

1. Python
1. Scala
1. C++
1. Other?

Fingers crossed!

