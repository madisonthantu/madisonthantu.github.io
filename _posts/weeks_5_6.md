---
layout: post
title: Weeks 5-6, *Building the Initial RS Model*
---

Equipped with our research proposal, the next step was beginning the actual implementation of the initial RS model. There are many different frameworks, packages, and toolkits available for building RSs, and the first implementation decision we had to make was deciding which of these existing tools to use for our own model. Ultimately, we decided to use the agent-based [t-RECS](https://github.com/elucherini/t-recs)[^1] simulation environment due to its ability to model dynamic user preferences. Additioanlly, we decided to use the MovieLens 100k dataset for our initial experiments and all experiments thereafter[^2]. To compute user and item embeddings, we used non-negative matrix factorization.

[^1]: https://arxiv.org/pdf/2107.08959.pdf
[^2]: https://grouplens.org/datasets/movielens/