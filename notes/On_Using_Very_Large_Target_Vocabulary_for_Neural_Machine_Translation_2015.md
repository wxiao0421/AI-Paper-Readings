NMT model with a large vocabulary size is slow while using a small vocabulary size usually has poor performance. This paper propose a method based on importance sampling to train NMT with a large vocabulary size by using approximately the same amount of time.

It work as follows:

Partition the training corpus and define a subset V of the target vocabulary for each partition prior to training. Before
training begins, we sequentially examine each target sentence in the training corpus and accumulate unique target words until the number of unique target words reaches the predefined threshold . The accumulated vocabulary will be used for this partition of the corpus during training. Basically the distribution Q used in the important sampling is 1/|V_i'| for all words in V_i' and it cancelled out.

The author point out that this choice of Q makes the estimator biased. Why?