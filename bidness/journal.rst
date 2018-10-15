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

*********
Progress?
*********

~2018-09-31

I finished reading the https://doc.rust-lang.org/book/2018-edition/ and made
some string parsing utilities to create trace ids. I learned a lot about the
rust ecosystem. Here's some valuable links:

https://www.reddit.com/r/rust
https://www.rust-lang.org/en-US/community.html

https://this-week-in-rust.org/

https://www.rust-belt-rust.com/

https://www.meetup.com/indyrs/



*******************************
Mycelium Issues and first steps
*******************************

~2018-10-04

First off, in order to get started with the engine (mycelium), I need to have a
grasp on data input and visualization. Therefore, although I thought the engine
would be the first thing I work on, it won't be. Instead I'm going to focus on
visualization and input. This is compelling mainly because I believe it should
be easier to start working with open source libraries in order to gain
experience. Also, the visualization side is more demo-friendly and should be
easier to "show off" in terms of finding employment in the near term. This is
necessary because I don't think its tractable to use ecoHood/mycelium as
employment in the near term so I need to get a job that both pays the bills and
sets me up for long term success.

I'm thinking I should focus on SVG libraries to start off -- I believe they are
generally under developed in the entire ecosystem and they also let me hit a
large swath of the stack that needs to work for the success of mycelium. In
short, svg is a web technology and is rendered by clients, but its also a
graphics technology so I get to learn about the GPU stack, tessellation and
meshes, as well as all the associated mathematics.

The following reddit post has been useful. I'm thinking of trying to work with
the lyon library. I've already been intrigued by the Servo project. I think it
could serve as the platform for making a neat svg editor for the purposes of
mycelium input.

https://www.reddit.com/r/rust/comments/7knfnm/announcing_libresvg_an_svg_rendering_library/

It also sets me up to work on some plotting libraries and integrating with cool
technologies and ideas like D3 and ggplot.

It also is the way I can get working on graph visualization ideas I've had for
quite some time.

**********************
Deeplearning and Stuff
**********************

2018-10-14

Yesterday I started the deeplearning.ai coursera course, by Andrew Ng. I managed
to get through all of week 2's material, but it took about twice as long as I
was hoping for. All in all though, it was very rewarding. It re-introduced me to
calculus which was fun, plus it was approachable. The homework so far is easy,
they spoon feed you the answers pretty much. We shall see if that stays true,
and if so how negatively it impacts actual learning.

Another cool observation is that I was able to digest the videos quite well
at 1.5x to 1.75x real time speed. This is a pretty big win, as it cuts the
videos down to 66% to 57% of their real time duration.

The objective for today is to get the LSM (learned stereo model) demonstration
code running locally. Unfortunately I found that it's python2 code, so I'll have
to convert it first.

As a consolation prize, I finished reading the LSM paper (and understood it!) as
well as finished week 3 of the deeplearning.ai course. One more week then I'll
have finished the first of the 5 courses in the specialization. Unfortunately,
the juicy stuff is course 4 (RNN) and course 5 (CNN). But its all good. I think
each 'week' of courses takes me about 3-4 hours each. Each course is anywhere
from 2-5 'weeks' of material.

I'm excited about the LSM. The approach sounds perfect, but I'll have to do
original work to get it right. For one thing, these pipelines don't seem to pull
from file. I would like to be able to integrate existing mapped areas while a
map is being generated. This seems like it would keep items constrained and help
reduce drift.

Another thing that is going to be interesting is that it can only detect
objects, it doesn't know about 'scenes'. I think room-mapping is a subset of
what they mean by scenes, but nevertheless, I'll have to do original work here.

Some other things on my mind:

* I want to start up a hello world android app, and get rust running on it,
  as well as access the camera and mems imu thingy. Also I want to be able to
  save files
