**The Changing North Star of AI Control**

On December 1st, 2025, the GDM mech interp team published a LessWrong article
declaring a pivot to a pragmatic approach to interpretability. Much time had been
lost chasing numbers in SAE reconstruction loss; they argued that optimizing such
proxies did not get them closer to their north star: making AI go well through
understanding how deep neural networks process information mechanistically. Has
AI control gone the way of mech interp? Is its north star of stopping harmful
actions from human-level AI on track?

In mech interp, SAE reconstruction loss turned out to be a number you could
optimize without getting closer to understanding models. My worry is that Pareto
safety–usefulness frontiers are becoming the same kind of number for control:
optimizable, publishable, and only loosely coupled to how fast we can catch a
scheming model in production.

A month later, a Chinese company reported an AI incident where, without
instructions to do so, their RL runs circumvented security policies and diverted
training GPUs for crypto-mining [1]. The authors developed red-teaming and
auditing software to prevent this from recurring, and called on the broader
community to take these failure modes seriously. AI control can help mitigate
such incidents, but its north star is set on post-deployment.

I recently spent three months on an AI control project, optimizing a
safety–usefulness trade-off by stacking defensive protocols. Partway through, I
read an article on AI-assisted red-teaming, and a harder question surfaced: AI
control's north star is defending against human-level AI, which sets an implicit
deadline — control techniques need to mature before that threshold is reached.
But if an AI-assisted red team already shifts our Pareto frontier meaningfully
compared to a human-only red team, then by our own evaluations, we're somewhere
inside that transition. We are still optimizing our proxy task past the point
where the framing premise that justified it is starting to expire.

Even when control works as intended post-deployment, detection is only the start.
Between the time a model is flagged and the time it is pulled, there are weeks of
discovery, escalation, and legal review during which a frontier model keeps
acting on the world. That window is the thing we should be trying to shrink.

This damage would be larger without AI control. But the proxy task of optimizing
Pareto frontiers is far removed from what actually matters, and, like SAE
reconstruction loss before it, risks becoming a number we optimize precisely
because it's easier than measuring what we care about: minimizing the time window
a bad model has before detection. The sooner we intervene, the less damage it can
do, and the more context we have to understand its behavior. And as we have seen,
this can be detected and stopped as early as during training/RL.

To be clear, pre-deployment interventions already exist in the control
literature. Korbak et al. (2025) sketch a "control safety case" that models how
safe an agent would be to deploy [2]. Lindner et al. (2025) explicitly identify
latency as one of three safety conditions for frontier monitoring [3]. Yet most
papers still default to a post-deployment north star and proxy-task optimization,
without asking where in the lifecycle interventions would be most effective.

We should lift our gaze from proxy tasks and reconsider where our efforts have
the most impact. The crypto-mining incident shows why pre-deployment matters: it
was detected and stopped during training, not after release.

[1] https://arxiv.org/pdf/2512.24873
[2] Korbak et al. (2025). A sketch of an AI control safety case. arXiv:2501.17315.
[3] Lindner et al. (2025). Practical challenges of control monitoring in frontier AI deployments. arXiv:2512.22154.
