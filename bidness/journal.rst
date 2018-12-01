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

****
DSSS
****

2018-10-16


I woke up today stressed. I'm doing too much but everything is fun, so I don't
know what to cut.

I'm thinking about Tim Ferriss' DSSS strategy for learning. I need to learn how
to apply it to this project in order to make enough room for household stuff,
Brandy stuff (soon to be family stuff?!!), SpaceX stuff, and job hunting
stuff. I need to cut back on the quantity here.

DSSS stands for:

Deconstruct

- Figure out the different pieces of your problem/endeavor

Selection

- Choose a subset of the endeavor to focus on


Sequence

- Consciously choose a routine, also consciously mix it up to train your brain
  better
- A key principle is to be data driven here. Treat each sequence permutation as
  a new test.

Stakes

- If there's no skin in the game, there's no reason for keeping with the
  program.

#############################################
Journal and references for learning POA infra
#############################################


Background on the threshold encryption used:
https://z.cash/blog/new-snark-curve


Background on why fully distributed consensus isn't possible:
https://www.the-paper-trail.org/post/2008-08-13-a-brief-tour-of-flp-impossibility/

Some slides/lessons on threshold encryption
http://www.tcs.hut.fi/Studies/T-79.159/2004/slides/L9.pdf

Binary Agreement paper
https://hal.inria.fr/hal-00944019v2/document

Submitted a pull request against #284 on 2018-10-30

**********************
Rust Meetup 2018-11-07
**********************

A good idea would be a tutorial for using debugging in rust, including
recommendations for improvements and a survey of ongoing developments.

A talk on the pinning api would be interesting according to Zach (purdue physics
guy). A thing that allows generator expressions to work (like list comprehension
in rust).


clap? parsing error

std has the error trait -- not jsut the std::io. Didn't see it

check out errorchain crate. Gives you the flexibility to print or wrap


*********************
IOT Meetup 2018-11-15
*********************

Pretty good turnout, initial convo with Sean from ?? (clearobject
competitor). Talked about


matterport -- $5k camera for doing mapping

omni automation -- what are they? There are some folks here from them "A smart
home automation platform" (Presented by Brandon Fischer).


Fullstack - Daniel - They offer turnkey HR solutions for startup
companies. Everything from compliance to payroll to hiring. Started at the
beginning of 2018.

Talked with Brandon from Omni, made plans to get coffee/lunch sometime to talk about the startup.


****************
Entry 2018-11-27
****************

I finished the Poa Network hiring assignment yesterday (Monday the 26th). I started the prior
saturday (on the 18th). It was supposed to take a day or two but took me most of the week to do. I
had to learn a lot about the tokio library to make it work. But, I ended up with a multi threaded
peer to peer chat service that can send binary messages and also has a built in ACK
protocol. Overall I'm disappointed with how this ended up, I probably won't get further interviews
-- but I do feel like it improved my abilities, which I appreciate. Its up to me in the next few
weeks to figure out how to make the best of this. Where do I go from here?


Much of my difficulty in moving forward has been defining where I want to end up. Space is not so
interesting anymore, and my interests now don't fit nicely into one word. The next few paragraphs
are to explore "my interests", hopefully that will help focus my next steps forward in searching for
work.

**Key words**: :emphasis:`Agency, cost, safety, heterogeneity, evolution, resilience,
interconnectedness, local dependencies`.

**Agency**: I don't like being told what to do. I like working on a team, but one where I feel like a
peer, not a servant. One of my interests is to make more of the world work on a peer-to-peer level.

**Cost**: My continuing interest in space has to deal with understanding the structures that makes
forward progress so cost-prohibitive. The monetary cost is a symptom of the underlying cost -- which
is due to 1) reaching consensus on the risk posed by the operation (launch or new development), 2)
understanding whats going on sufficiently to decide what to do next. Consensus is a function of each
decision makers certainty of knowledge of how the system *should* work as well as their
understanding of how it *will* work. Certainty of knowledge is exponentially more difficult to
achieve the more complex the system is, and the smaller the priors are which help to inform both the
*should* and *will*, the higher the cost and the higher the system's risk. Note that I use space as
an example just because of familiarity, but the same goes for new product development efforts in
most fields.

**Safety**: This is a derivative of my rant on cost above

**Heterogeneity**: This is an offshoot of the rant on cost, plus agency. Because most interesting
things are more and more complex (spaceships, biology, computer hardware), the number of unique
developments and R&D in these fields is low. This is because team sizes go up, which raises costs,
which raises risk of failure. I want to be an artist/artisan. An artist because an artist has to
constantly innovate and change, and an artisan because heterogeneous peer-to-peer interactions are
encouraged for artisan buisinesses, rather than discouraged. But I want to be a technology
artist/artisan, which means something about the equation must change. I believe the best case-study
in how such a life can work is with small software development. Software development is working on
top of the tallest stack of man-made complexity ever imagined. What makes it work? How can other
industries be changed to more resemble individual software development?

**Evolution**: This is a derivative of heterogeneity. With more artisans in technology, that means more
players, which means more innovation due to competition and cooperation.

**Resilience**: Another derivative of heterogeneity. With more players, there are less single points of
failure due to a diversity of techniques and a diversity of resource dependencies.

**Interconnectedness:** A symptom of disease in our modern culture is our lack of natural community.
Community has become like gardening -- its something people do as a hobby rather than a necessary
piece of existence. Healthy people need tribes. Our economy has no need for tribes, so we all
suffer. I think more artisan careers would encourage local dependencies out of necessity which would
help communities stay connected with one another. The internet should supplement person-to-person
interconnections, but face-to-face needs to stay primary to minimize suffering.

**Local Dependencies**: A derivative of interconnectedness, emphasizing physical interaction rather
than just digital.

To me, that sums up my interests. It also seems like a coherent definition that lacks a term. I want
to change how economies work in order to incentivize economic evolution through increasing
*subjective* [#]_ agency, *subjective* heterogeneity, and *subjective* interdependence. The largest factor
discouraging that change is operational risk caused by uncertainty of outcomes.

Metaphorically, I see our society/economy/culture as functioning similar to a savanna now -- it's
characterized by large herds of homogeneous species (individuals within corporations and nation
states). I would prefer to live in a rainforest society/economy/culture -- characterized by a broad
array of interdependent and unique species thriving individually or in small tribes. In terms of
economic productivity and stability, I believe such a society/economy/culture would be more
productive and resilient -- just as a rainforest has more diversity and biomass than a savanna. Note
that over time a savanna becomes a rainforest provided sufficient raw materials. This is still
analogous to where we're heading where I believe we are getting closer to a post scarcity economy.

.. [#] I use *subjective* rather than *human*, because I believe a potential solution lies along
       supplementing human capabilities with machines. This is where my primary interest in AI and
       internet of things lies. These tools are double edged swords though, because they are
       dependencies, and therefore can become a way to control or restrict agency by controlling or
       restricting access to them.

