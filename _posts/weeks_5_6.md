---
layout: post
title: Weeks 5-6, *Building the Initial RS Model*
---

Equipped with our research proposal, the next step was beginning the actual implementation of the initial RS model. There are many different frameworks, packages, and toolkits available for building RSs, and the first implementation decision we had to make was deciding which of these existing tools to use for our own model. Ultimately, we decided to use the agent-based [T-RECS](https://github.com/elucherini/t-recs)[^1] simulation environment due to its ability to model dynamic user preferences. Additioanlly, we decided to use the MovieLens 100k dataset for our initial experiments and all experiments thereafter[^2]. To compute user and item embeddings, we used non-negative matrix factorization (NMF).

Recall that two of the dynamics of interest in our study were filter bubbles and user behavior homogenization. During this phase of our research project, we had to operationalize these two RS properties. For filter bubbles, we decided to do this by using the *k*-means clustering algorithm on the item embeddings computed via NMF, the results of which we called *topic clusters*. We used these topic clusters to implement several of our diversity-promoting recommendation algorithms as well as define several of our exploration-related measurements. For the dynamic of user homogenization, we were in particular interested in how said homogenization varied within a particular filter bubble versus at the global level. To operationalize these intra- versus inter-filter bubble dynamics, we needed a way to map users to a particular filter bubble. We implemented this by assigning each user to the topic cluster that minimized the euclidean distance between the user embedding and the topic cluster centroid.

After we made these implementation decisions, we were able to run our first simulation using the T-RECS framework. From here, we were able to begin the hyperparameter tuning phase, specifically examining how modifying the hyperparameters of *drfit* and *attention exponent* effected the simulation evolution.

[^1]: https://arxiv.org/pdf/2107.08959.pdf
[^2]: https://grouplens.org/datasets/movielens/