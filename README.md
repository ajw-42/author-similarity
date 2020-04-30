# author-similarity
This repo looks at a few different ways of measuring similarity among authors of social media posts. These approaches might be helpful for quantifying similarity among known users or for identifying new users who are similar to a group of known users.

I use two Kaggle datasets: one of [Reddit posts] (https://www.kaggle.com/rootuser/worldnews-on-reddit/data) in the r/worldnews subreddit from 2008 to 2017 and another of [Twitter posts](https://www.kaggle.com/kapastor/democratvsrepublicantweets) from US politicians.

Approaches used:
- word2vec embeddings trained from scratch and LASER pre-trained embeddings to create user-level vectors.
- Cosine distances, FAISS, T-SNE, and k-means clustering to measure/visualize similarity.

The LASER embeddings with the FAISS similartiy metrics appear to perform best. However, even for these relatively small datasets, LASER requires GPU support while word2vec runs fine on CPU even when training from scratch and the results are stil good.

Here's a quick summary of the results:

**Twitter dataset**

**Reddit dataset**

| Original Author  | Most Similar Authors | Embedding Method | Similarity Metric
| ------------- | ------------- | ------------- | ------------- |
| 000078754  | florence25, marcpk, dreams16, tefster | word2vec (trained from scratch)  | cosine distance |
| 000078754 | fishbert, dougmataconis, madonix, C2hristina | word2vec (trained from scratch)  | FAISS |
| 000078754 | dredd, pookie74, fitqueenb, downgoesfrazier | LASER (pre-trained embeddings) | cosine distance |
| 000078754  | fellowmellow, polar, nebm, theseusastro | LASER (pre-trained embeddings) | FAISS |
| 007simple  | goghi, coffinman82, charlatan, Dhghomon | word2vec (trained from scratch)  | cosine distance |
| 007simple | clacla83, glcarlstrom, casualfactors, XKingKong | word2vec (trained from scratch)  | FAISS |
| 007simple  | stavromullerbeta, AvicusGottskalk, matthew26, pookie74 | LASER (pre-trained embeddings) | cosine distance |
| 007simple  | splunge4me2, polar, markvand, reeds1999 | LASER (pre-trained embeddings) | FAISS |
| 00boyina  | geekchic, chefranden, silence_hr, viborg | word2vec (trained from scratch)  | cosine distance |
| 00boyina | garyp714, cfall123, shravanmishra, vanibahl | word2vec (trained from scratch)  | FAISS |
| 00boyina  | joelrw, cup, jimmurphysf, kcnchfan | LASER (pre-trained embeddings) | cosine distance |
| 00boyina  | jms1225, karthikmns, dulieu, NoNoLibertarians | LASER (pre-trained embeddings) | FAISS |
| 02116663ag  | IntolerantFaith, NagastaBagamba, sohail, stubble | word2vec (trained from scratch)  | cosine distance |
| 02116663ag | ImJulianAssange, MrXfromPlanetX, smag1985, steppenwolf86 | word2vec (trained from scratch)  | FAISS |
| 02116663ag  | sam1426, samblesj, louis_xiv42, Laserfalcon | LASER (pre-trained embeddings) | cosine distance |
| 02116663ag  | sadbuttru, safishb, escape_goat, telefonbesked | LASER (pre-trained embeddings) | FAISS |
| 0boy  | gtfonline, rastawala, sea_wall, ajehals | word2vec (trained from scratch)  | cosine distance |
| 0boy | gregwont, rajsaxena, saute, aenea | word2vec (trained from scratch)  | FAISS |
| 0boy  | Kyusu, Imagineti, pastr, dzneill | LASER (pre-trained embeddings) | cosine distance |
| 0boy  | dynamohum, Kleenex1, louis_xiv42, mhughes3500 | LASER (pre-trained embeddings) | FAISS |
