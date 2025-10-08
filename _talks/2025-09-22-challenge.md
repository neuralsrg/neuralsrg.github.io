---
title: "4th Place Solution in RecSys Challenge 2025"
collection: talks
type: "Talk"
permalink: /talks/2025-09-22-challenge
venue: "RecSys'25 - O2 Universum"
date: 2025-09-22
location: "Prague, Czech Republic"
---

[Slides can be found here](https://neuralsrg.github.io/files/RecSys_Challenge_2025.pdf)

Transcription
======

1. About the data
------
The challenge was centered on a large-scale e-commerce platform. Participants were given around 200 million user-item interactions collected over roughly six months. These interactions were highly imbalanced. Most -- about 90% -- were page visits. The remaining 10% included search queries, cart additions, and cart removals, with purchases being relatively rare.

The task was to generate user embeddings, referred to as Universal Behavioral Profiles. These embeddings were intended for server-side use in training six separate models - each corresponding to a different evaluation task.


2. Solution overview
------
We stacked embeddings from four diverse models. These included a transformer-based sequential encoder and a graph neural network developed by former Twitter researchers, refered to as TwHIN. In addition to that, we engineered around 300 numerical features and modeled interactions between them using a Deep Cross Network.


3. Sequential Encoder
------
We represent each user as a sequence of their interactions of all types ordered by timestamp. We then feed this sequence into a Transformer model with a causal mask. The final hidden state of the Transformer is used as the user’s representation.


4. Sequential Encoder
------
Cart additions, removals, and purchases are all item-related interactions, so we encode them in a similar way. Due to the high cardinality of SKU and category IDs, we apply a hashing function and map the results to an embedding table with 500,000 entries. To reduce collisions, we use two different hashing functions with separate seeds and concatenate the resulting embeddings. This technique, originally proposed by Google, is known as Multisize-Unified Embeddings.

For other features like price, item name, and search queries—which were already tokenized by the organizers—we simply used learnable token embeddings for each token ID. URL IDs were handled similarly using the multihash technique with the same embedding table.


5. Sequential Encoder 
------
We trained this model to predict both the type of the next interaction and the time elapsed since the previous one.

If the next interaction is item-related, we also predict the exact item using a sampled softmax loss with log-Q correction to account for item popularity. For page visits, we predict the next URL ID using a standard sampled softmax, as the target space is dense.


6. TwHIN 
------
Next, we adopted a Graph Neural Network to learn user embeddings. We chose the model proposed by former Twitter researchers, known as TwHIN, due to its relatively simple parameterization and its ability to handle multiple edge types.

We built a bipartite user-item graph, where edges represented cart additions and purchases. For item embeddings, we used the pretrained content encoder from the sequential model. We used 1.5M learnable embeddings for users with the most interactions including those required for evaluation. 


7. TwHIN 
------
The core idea behind TwHIN is straightforward. First, the user embedding is normalized. Then, the item embedding is combined with a relation embedding corresponding to the edge type, and the result is also normalized. The probability of an edge is then modeled using the sigmoid of the dot product between the user and item embeddings.

We trained the model on link prediction task using binary cross-entropy loss with in-batch negatives. This means that for each user in the batch, we treat edges to items from other samples in the batch as negative examples.


8. Handcrafted Features
------
Next, we focused on mining handcrafted features, which we grouped into two categories.

The first group consisted of simple counters and averages calculated over five different time windows: the last 7, 14, 28, and 60 days, as well as the entire dataset period. Each feature was computed across all five intervals, resulting in 205 features in total.

The second group involved aggregations over thematic and price-based clusters. Here, we applied exponential weighting during aggregation to give more importance to recent interactions.

The final numeric feature vector was standardized to match the scale and distribution of the neural network embeddings.

We included an appendix in the paper that details each numeric feature.


9. Deep Cross Network 
------
Finally, we used a Deep & Cross Network to model interactions between the sequential and numeric feature embeddings.

We embed the sequential data with the frozen sequence encoder.

To transform the numeric features, we applied a method called PLE, which is quite simple: each numeric value is first split into 65 intervals based on 64 quantiles. Each of these intervals is then subdivided uniformly into 32 subintervals. The resulting quantization ID is mapped to a 2-dimensional embedding, which gives an input dimensionality that is twice the number of features. 

We then concatenated the sequential and numeric embeddings and passed the result through a DCN-v2 module followed by a DenseNet.

This model was trained on the disclosed tasks: churn prediction, SKU propensity, and category propensity. The main challenge here was the extreme sparsity of the target labels.


10. Deep Cross Network 
------
To help the model learn more meaningful representations, we incorporated contrastive learning.

We applied random masking to each user sequence twice, with a 30% probability of masking each interaction. These two augmented sequences were then processed as usual—through the sequential encoder and embedding pipeline.
We treated the resulting pair of embeddings as positive examples and used a sampled softmax loss with in-batch negatives for training. The best part is—it actually worked. It significantly improved our offline metrics.


11.  Key ablation insights
------
Finally, our research contained a lot of ablations studies, and here we list the key insights to mention: 
1. Omitting any model from the ensemble drops quality 
2. For sequential encoder, NIP appeared to be a most critical objective, even though 90% of interactions were page visits 
3. Scaling sequential encoder size improved metrics 
4. For GNN, cart additions provided an important signal on top of purchases 
5. And, as mentioned before, contrastive learning helped us tackle sparsity issues.
