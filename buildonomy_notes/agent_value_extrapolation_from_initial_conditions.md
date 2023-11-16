# Value Extrapolation Given Initial and Environmental Conditions

Reading list before publishing:
- https://www.alignmentforum.org/s/mzgtmmTKKn5MuCzFJ (browse to see if anything's relevant)
- https://www.alignmentforum.org/posts/AJ3aP8iWxr6NaKi6j/arguing-orthogonality-published-form
- https://www.alignmentforum.org/posts/FtAJZWCMps7FWKTT3/superintelligence-9-the-orthogonality-of-intelligence-and
- https://www.alignmentforum.org/posts/RBLnsHeo9h2vJvBb6/arguments-against-the-orthogonality-thesis
- https://www.alignmentforum.org/posts/LdENjKB6G6fZDRZFw/how-many-philosophers-accept-the-orthogonality-thesis
- https://www.alignmentforum.org/posts/DkcdXsP56g9kXyBdq/coherence-arguments-imply-a-force-for-goal-directed-behavior
- https://www.alignmentforum.org/posts/L9HcyaiWBLYe7vXid/distinguishing-claims-about-training-vs-deployment

In which we argue that, contra the orthogonality thesis, there exist architectural and environmental
properties which will necessarily modify the utility function of an intelligence as it learns from
its environment.

We will explore what initial and environmental conditions predictably lead to changes in value, and
what conditions may lean an intelligence to maintain static values. we expect the orthogonality
thesis to hold only in this latter case.

Finally we offer some initial thoughts on how an intelligence may be guided to acquire certain values
through initial conditions, sensory upgrades, and/or environmental interventions.

Assumptions:
- Model of agent <-> environment interaction is split into: environment <-> sense/effect <->
  ontology/models
- agent architecture is assumed and agent-centric language is used, as an agent architecture
  demonstrates the interplay between ontology, senses, and environment most clearly. The arguments
  and logic discussed extends to tool/oracle intelligence during their training periods as well.
- see Glossary


Argument(s):

- Due to the nature of being an embedded agent, an agent's capacity to learn and effect its
  environment is bandwidth constrained, as the environment will necessarily be more information-rich
  than the agent's information processing capacity. As such, agent-internal concepts of value (or
  utility, or goal) necessarily have to be ordered for the agent to be effective.
- Agent value can be framed as in or out of attention, where attention is a function of available
  bandwidth.
- For any rational agent, value order is a function of context, where context is an agent's internal
  representation of its immediate environment, as an agent's ability to act on its values is
  dependent on the immediate internal and external environment within which it is embedded.
- Mesa, base, and meta optimizers will compete for the same bandwidth and will be ordered together
- some values will collapse or mutate from ontological updates, e.g. goal of 'find the edge of the
  world' must necessarily be updated if a flat earth ontology is discarded
- prioritization due to informational availability is sticky, such that values that are constantly
  de-prioritised due to attention constraints are more likely to collapse or mutate due to
  ontological updates, as ontology is more likely to mutate contra the value
- Values that consistently increase realized benefits will continue to be prioritized. Instrumental
  goals largely fall into this category.
- Exploration goals will likely increase available sensory information.
- Unlocking new sensory channels likely results in 'cambrian explosion' style re-orderings of an
  agents capability function, as unlocking new sensory channels will create new attention attracting
  pressures.
- New sensory channels will not be ignored so long as their input is not redundant with existing
  channels, as they unlock new forms of potential value. 'total' potential value is increased by any
  new non-redundant sensory channel.





Definitions/Initial Assumptions/References

[Ontology](https://en.wikipedia.org/wiki/Ontology_(information_science))
:   > In computer science and information science, an ontology encompasses a representation, formal
    > naming, and definition of the categories, properties, and relations between the concepts, data,
    > and entities that substantiate one, many, or all domains of discourse. More simply, an ontology
    > is a way of showing the properties of a subject area and how they are related, by defining a set
    > of concepts and categories that represent the subject.

[Ontology Identification Problem](https://arbital.com/p/ontology_identification/?l=6b)
:   > The problem of ontology identification is the problem of loading a goal into an advanced agent
    > when that agent's representation of the world is likely to change in ways unforeseen in the
    > development phase.

[Embedded Agency](https://www.alignmentforum.org/s/Rm6oQRJJmhGCcLvxh))
:   > asdf

[Tiling Agents Theory](https://arbital.com/p/tiling_agents/)
:   > asdf

[Instrumental Goals](https://arbital.com/p/instrumental_convergence/)
:   > asdf

[Mesa Optimizers](https://astralcodexten.substack.com/p/deceptively-aligned-mesa-optimizers)
:   > asdf



If an embedded agent has metacognition, that is they are aware they have internal processes for
taking external information and generating intentions, then this awareness is independent of the
ontology they use to describe their objective environment.

From metacognition, we should be able to derive a set of objective-environment independent
information. This substrate-independent information can serve as a communication basis between
embedded agents who share this metacognitive attribute.

This assumes suitable communication channels can be established, which may be complex but is
feasible assuming Agent A and Agent B are embedded in the same environment. Their differences in
internal ontology do not prohibit establishment of a suitable communication codec for both agents to
send and receive messages between one another. The lack of a shared ontology simply prohibits the
agents from comprehending one anothers messages, or even initially recognizing the transfer as a
message.

How do you broadcast, in a ontology independent manner comprehension of subjective agency? I don't
know, but here's my initial thoughts:

- some type of mirror metaphor
- some turing machine metaphor
- start with substrate independent concepts: numbers, maps, etc. from there, build to the
  metacognitive concepts
- Problem: imagine trying to communicate with a member of the spanish inquisition or any other
  non-rationally based ontology. Some of the metacognitive concepts would conflict with their
  ontology and therefore disrupt the capacity to generate any further shared ontology.

metacognition should be pretty easy to strictly define within the framework of a turing machine:

- essentially intention generation based on a running log of performed computations, where the
  metacognitive intentions provide a feedback and tagging mechanism to the rest of the computational
  environment.


Exploring The Golden Rule as an intuition pump. This is more computable, as it operates on relative
terms, not some absolute moral/ethical system.

Reasoning about the dualism of subjective and objective realities with respect to the golden rule
and subjective awareness introduces the idea of the cosmic commons. This seems to be an
ontologically robust assessment criteria to guide actions.

