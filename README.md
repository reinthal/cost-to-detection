**The Fading North Star of AI Control**

On December 1st, 2025, the GDM mech interp team published a LessWrong article
declaring that they were pivoting to a pragmatic approach to interpretability.
Much time had been lost chasing numbers in SAE reconstruction loss; they argued
that optimizing such proxies did not get them closer to their north star: making
AI go well through understanding how deep neural networks process information at
a mechanistic level. Has the AI control agenda gone the way of mech interp? Is
its north star of stopping harmful actions from human-level AI on track to
provide us the tooling to do so?

The parallel I want to draw is this: in mech interp, SAE reconstruction loss
turned out to be a number you could optimize without getting closer to
understanding models. My worry is that Pareto safety–usefulness frontiers are
becoming the same kind of number for control: optimizable, publishable, and
only loosely coupled to how fast we can catch a scheming model in production.

About a month later, a Chinese company published an article detailing an AI
incident where, without implicit or explicit instructions, their RL runs
circumvented security policies and diverted training GPUs for crypto-mining [1].
The authors subsequently developed red-teaming and auditing software to prevent
this from happening again, and issued a call to the broader community to pay
attention to these kinds of failures when developing advanced AI systems. I
think the AI control agenda can serve us well to mitigate such incidents, but
its north star is set on post-deployment.

I recently worked on a project in AI control, where we devoted three months to
optimizing a trade-off between safety and usefulness by stacking defensive
protocols. After reading an article on AI-assisted red-teaming, it was clear to
me that if we wanted an accurate Pareto frontier, we needed to do something
similar: human red-teaming efforts alone would not be enough to get an accurate
picture of how much security our protocols were providing. This made me think
that our proxy task of Pareto-frontier optimization had become misaligned with
the north star of AI control.

And even when control works as intended post-deployment, detection is only the
start. Between the time a model is flagged and the time it is actually pulled,
there are weeks of discovery, escalation, and legal review during which a
frontier model keeps acting on the world. The damage accumulated in that window
is the thing we should be trying to shrink.

This damage would certainly be larger without AI control. However, the proxy
task of optimizing Pareto frontiers is far removed from what actually matters,
and, like SAE reconstruction loss before it, risks becoming a number we optimize
precisely because it's easier than measuring the thing we care about: minimizing
the time window a bad model has before detection. The sooner we intervene, the
less damage it can do, and the more context we have to accurately understand its
behavior. And as we have seen, this can be detected and stopped as early as
during training/RL.

I think AI control needs to redefine itself, and set a new north star: AI
control should find points of intervention throughout the model lifecycle,
hopefully preventing incidents like this before deployment. That way, AI control
could provide more benefit today, and be more resistant to going the way of the
ambitious mech interp era, where every paper was about SAEs and reconstruction
loss.
