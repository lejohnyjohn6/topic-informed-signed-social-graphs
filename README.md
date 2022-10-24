# Learning Stance Embeddings from Signed Social Graphs
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-green.svg?style=flat-square)](http://makeapullrequest.com)
[![arXiv](https://img.shields.io/badge/arXiv-2201.11675-b31b1b.svg)](https://arxiv.org/abs/2201.11675)

This repo contains the code and datasets from our paper: [Learning Stance Embeddings from Signed Social Graphs]([https://arxiv.org/abs/2209.07562](https://arxiv.org/abs/2201.11675)).
[[PDF]](https://arxiv.org/pdf/2201.11675.pdf)
[[HuggingFace Datasets]](https://huggingface.co/Twitter)

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

## Overview
A key challenge in social network analysis is understanding the position, or stance, of people in the graph on a large set of topics. In such social graphs, modeling (dis)agreement patterns across a range of correlated topics may be beneficial. Indeed, disagreement on one topic may make disagreement (or agreement) more likely for related topics. 
The **Stance Embeddings Model (SEM)** jointly learns embeddings for each user and topic in signed social graphs with distinct edge types for each topic. By doing so, SEM is able to **unveil topic alignments and perform cold-start topic stance detection**, predicting the stance of a user on topics for which their engagement has never been observed.
We open source **two Twitter signed, topical graph datasets**. One dataset, **TwitterSG**, labels (dis)agreements using engagements between users via tweets to derive topic-informed, signed edges. The other, **BirdwatchSG**,leverages community reports on misinformation and misleading content.

## Datasets

### TwitterSG

Twitter Signed Graph, or TwitterSG, is a signed, directed, edge-attributed graph of users, drawn from Twitter interactions. TwitterSG contains 753,944 nodes (users), 200 topics and 12,848,093 edges. It is the largest publicly available user-to-user signed social graph (∼6x larger than the Epinions graph).

A positive signed edge exists from user 𝐴 to user 𝐵 if user 𝐴 liked a tweet. posted by user 𝐵. A negative-signed edge exists from user 𝐴 to user 𝐵 if user 𝐴 expressed opposition towards user 𝐵’s tweet, e.g., by replying I disagree with you. The topic of an edge from user 𝐴 to user 𝐵 is determined by the topic of user 𝐵’s tweet, also called the target tweet. 
Tweets' topics were inferred with a topic classifier used in production by Twitter. Provided topics are all related to sports (e.g., sports teams, players, managers, or events), and the tweets related to these interactions were published between 20th May (Ice Hockey World Championships) and 8th August 2021 (closing date of the 2020 Tokyo Olympic Games). 
9.6\% of edges are negative (opposition) and 90.4\% are positive.  The data format is displayed below.

| source_node | target_node | topic | sign |
| ------------- | ------------- | --------- | ---- |
| 1   | 6 | Copa America | +1 |
| 1   | 6 | NFL | -1 |
| 4   | 5 | Kylian Mbappe | +1 |

### BirdwatchSG

Birdwatch Signed Graph, or BirdwatchSG, is a signed, directed, edge-attributed graph of users, drawn from note ratings on [Birdwatch](https://blog.twitter.com/en_us/topics/product/2021/introducing-birdwatch-a-community-based-approach-to-misinformation). Birdwatch is a pilot launched by Twitter in January 2021 in the USA to address misleading information on the platform, in a community-driven fashion: the Birdwatch participants can identify information in tweets they believe is misleading and write notes that provide informative context. They can also rate the helpfulness (either helpful, somewhat helpful, or not helpful) of notes added by other contributors. All Birdwatch contributions are publicly available on the Download Data page of the [Birdwatch site](https://twitter.github.io/birdwatch/) so that anyone in the USA has free access to analyse the data.


## Citation
If you use SEM or our datasets in your work, please cite, please cite the following:
```bib
@article{pougue2022learning,
  title={Learning Stance Embeddings from Signed Social Graphs},
  author={Pougu{\'e}-Biyong, John and Gupta, Akshay and Haghighi, Aria and El-Kishky, Ahmed},
  journal={arXiv preprint arXiv:2201.11675},
  year={2022}
}
```
