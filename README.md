# Word-Sense-Disambiguation

## Task description

The full description of the task can be found here: https://nlpub.github.io/russe-wsi-kit/.

The results of the in-class competition after the official deadline of the main competition are presented here: https://competitions.codalab.org/competitions/36019#results.

In the competetion were used three datasets:

1) **wiki-wiki**: This dataset contains contexts from
Wikipedia articles. The senses of this dataset correspond to a subset of
Wikipedia articles.

2) **bts-rnc**: This dataset contains contexts from the
Russian National Corpus (RNC). The senses of this dataset correspond to the
senses of the Gramota.ru online dictionary (and are equivalent to the senses of
the Bolshoi Tolkovii Slovar, BTS).

3) **active-dict**: The senses of this dataset
correspond to the senses of the Active Dictionary of the Russian Language a.k.a.
the ‘Dictionary of Apresyan’. Contexts are extracted from examples and
illustrations sections from the same dictionary.


## My scores

**wiki-wiki** dataset: 3/11

**bts-rnc** dataset: 4/13

**active-dict** dataset: 1/13

## Methodology

1) After text preprocessing I firstly take the baseline solution of this contest from here https://github.com/akutuzov/russian_wsi 

   The solution is as follows:

   In each cluster of words (here I mean, for instance, all meanings of word 'замок') we take the vector embeddings of each word of the context with the      function fingerprint() and take the mean of the sum of the vectors.

   The resulting vectors are then ran through two step-clustering by the function predict_clusters(): first, with Affinity Propagation to evaluate the        amount of clusters and after that the eastimated amount of clusters is used in Spectral Clustering.

2) The upgrade of the baseline solution is
   - trying different corpora, including those without position tagging
   - trying different clustering hyperparametes + changing at the second step Spectral Clustering to KMeans Clustering

