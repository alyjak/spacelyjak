## Assessment Of Current State Of The Art

2022-04-05

I see the state of the art as defined by the following (knowingly availability biased):

- State of the art large language model performance: https://ai.googleblog.com/2022/04/pathways-language-model-palm-scaling-to.html
- State of the art training/physical architecture: https://blog.google/technology/ai/introducing-pathways-next-generation-ai-architecture/
- Current trends in scaling laws: https://www.lesswrong.com/posts/midXmMb2Xg37F2Kgn/new-scaling-laws-for-large-language-models
- Compute comparison to human brain: https://www.openphilanthropy.org/brain-computation-report

Based on above, I assume that:

- human brain performs ~10^17 FLOP/s
- human "training" occurs for ~20years, but I'll assume that half of the 20 years is necessary for
  training, presuming that living and training are highly correlated but not synonymous. This is 3.15*10^8s
- human brain needs ~3.15*10^25 FLOPs to reach a "trained" state.

PaLM 540B parameter model was trained with ~2.52*10^24 FLOPs

I don't know how to compare training 'tokens' to human input (my understanding is these are input
data batches, normalized somehow).

According to current trends in scaling laws, PaLM was under-trained, and would achieve optimal
benchmark performance with a training budget of ~4*10^25 FLOPs. This suggests an analogy where the
benchmark performance for this model at this level of training could be compared to testing a two
year old.

Even so, the model was able to surpass average performance of 9-12 year olds on grade-school math problems:

> For example, with 8-shot prompting, PaLM solves 58% of the problems in GSM8K, a benchmark of
> thousands of challenging grade school level math questions, outperforming the prior top score of 55%
> achieved by fine-tuning the GPT-3 175B model with a training set of 7500 problems and combining it
> with an external calculator and verifier.
>
> This new score is especially interesting, as it approaches the 60% average of problems solved by
> 9-12 year olds, who are the target audience for the question set. We suspect that separate encoding
> of digits in the PaLM vocabulary helps enable these performance improvements.

Obviously this isn't a real comparison for a variety of reasons, notably the difference in training
corpus for this model versus the corpus we humans train on.

Nevertheless, I think these references enable some pretty strong predictions about language model
performance in the next few years.

- First, the available compute sufficient to train these models is limited, so we can assume state of
  the art results (*in this paradigm*) will only come from well resourced institutions.
- PaLM 540B took ~1500 hours (2mo) to train. Until researchers are highly confident of meaningful
  success, wall times much greater than this for training are unlikely.
- SWAG: Compute could possibly improve 10x in the next few years if large institutions are focused (which
  they are) on state of the art AI models
- May be able to produce a scale optimal 0.5 T parameter model in the next few years

If I don't think AGI is occurring in the next decade, what do I project the capabilities of a
next-gen language model, trained in 2025 by Google for 4 months wall-time off the best and largest
corpus of material to be?

I think we can back track what that model will look like in terms of scale. The parameter that seems
most limited to scaling in the next few years is the training data. I think it's fair to assume that
the percentage of human knowledge captured in the current corpus will not increase by more than
~20%, so that the non-redundant training 'tokens' available is unlikely to increase by more than
.. lets say 2x to be conservative.

So, from this, in ~2 years, Google may be able to allocate 4mo of 10x the compute used on PaLM,
that's 4mo at 20 exaFLOP/s = 20 * 10^18 * 4*30*24*60*60 = 2.07*10^26 FLOPS.

Consulting
https://www.lesswrong.com/posts/midXmMb2Xg37F2Kgn/new-scaling-laws-for-large-language-models, they
could then train ~ 1Trillion parameter model optimally IF they had a corpus of ~21 Trillion
tokens. I think it's likely we only have ~2 T good tokens in a couple years.

Then again, architecture updates could make models multi-modal -- that seems to be part of the
purpose of the pathways architecture. This could expand the 'type' of tokens available, and
therefore expand the knowledge base to reach an equivalent of this 21 Trillion token number.

Also, I think it's likely that
https://ai.facebook.com/blog/self-supervised-learning-the-dark-matter-of-intelligence/ gets
incorporated into state of the art models in the next couple years. This could drastically reduce
the necessary size of the training corpus.

Given all of this, I'm going to say it's likely that an 'ideal' model of this size is available in
two years. I'm also going to assume the log-linear trendline plotted in "Scaling behavior of PaLM on
a subset of 58 BIG-bench tasks." within
https://ai.googleblog.com/2022/04/pathways-language-model-palm-scaling-to.html continues.

Given this, and assuming the BIG-bench is a suitable proxy of comprehension intelligence, then the
model will have the comprehension capacity of approximately an 85th percentile human. What will this
mean?

- non-creative bureaucratic jobs can be replaced by the model, but then again, most non-creative
  bureaucracy can be replaced by traditional software.
- non-creative software jobs can be replaced by the model.


So what's missing?
- can it incorporate new knowledge or is it static post-training?
- I think subjective/objective awareness is still necessary
- I think there is something about symbolic negative space that's missing -- ontology creation might
  be it. Something around awareness of subjective symbolic space, and having the capacity to imagine
  different configurations of that space, and interplay that with some facet of objective
  experience. That facet could be a dialogue/conversation, a science experiment, an artistic
  representation of the internal symbology, etc.

  The generative art so far is interesting, but it takes randomness as its initial input, then molds
  that into representations of internal symbology -- keeping the internal state unadultered.

it may be that the only missing piece of AI is mixing training with execution. Once that divide is
merged, the self-mutation may result in AGI capacity.

If that's the case, I think the utility functions around subjective/objective divides is necessary
for both alignment, as well as the model's capacity to not self-degrade.

