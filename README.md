[![INFORMS Journal on Computing Logo](https://INFORMSJoC.github.io/logos/INFORMS_Journal_on_Computing_Header.jpg)](https://pubsonline.informs.org/journal/ijoc)

#  [Product Redesign and Innovation Based on Online Reviews: A Multistage Combined Search Method](https://doi.org)

This archive is distributed in association with the [INFORMS Journal on
Computing](https://pubsonline.informs.org/journal/ijoc) under the [MIT License](LICENSE).

The software and data in this repository are a snapshot of the software and data
that were used in the research reported on in the paper 
[Product Redesign and Innovation Based on Online Reviews: A Multistage Combined Search Method](https://doi.org) by J. D. Qin, P. Zheng, and X. J. Wang.

## Cite

To cite this software, please cite the [Jindong Qin, Pan Zheng, Xiaojun Wang. Product Redesign and Innovation Based on Online Reviews: A Multistage Combined Search Method, INFORMS Journal on Computing.](https://doi.org)

Using its DOI and the software itself, using the following DOI.

[![DOI](https://zenodo.org/badge/574702645.svg)](https://zenodo.org/badge/latestdoi/574702645)

Below is the BibTex for citing this version of the code.

```
@article{Redesign2022,
  author =        {J. D. Qin, P. Zheng, and X. J. Wang},
  publisher =     {INFORMS Journal on Computing},
  title =         {Product Redesign and Innovation Based on Online Reviews: A Multistage Combined Search Method},
  year =          {2023},
  doi =           {10.5281/zenodo.7407123},
  note =          {https://github.com/INFORMSJoC/2022.0333},
}  
```

## Abstract

Online reviews published on the e-commerce platform provide a new source of information for designers to develop new products.
Past research on new product development (NPD) using user-generated textual data commonly focused solely on extracting and identifying product features to be improved. However, the competitive analysis of product features and more specific improvement strategies have not been explored deeply.
This study {fully uses} the rich semantic attributes of online review texts and proposes a novel online review--driven modeling framework. This new approach can extract fine-grained product features; calculate their importance, performance, and competitiveness; and build a competitiveness network for each feature. As a result, decision-making is assisted, and specific product improvement strategies are developed for NPD beyond existing modeling approaches in this domain.
	Specifically, online reviews are first classified into redesign- and innovation-related themes using a multiple embedding model, and the redesign and innovation product features can be extracted accordingly using a mutual information multilevel feature extraction method.
	Moreover, the importance and performance of features are calculated, and the competitiveness and competitiveness network of features are obtained through a personalized unidirectional bipartite graph algorithm.
	Finally, the importance—performance—competitiveness analysis plot is constructed, and the product improvement strategy is developed via a multistage combined search algorithm.
		Case studies and comparative experiments show the effectiveness of the proposed method and provide novel business insights for stakeholders, such as product providers, managers, and designers.

## Description
Figure below shows the framework of the methodology, which is composed of three phases as follows:
	
- Phase 1. Extract product features related to product redesign and innovation.

- Phase 2. Calculate each feature's importance, performance, and competitiveness, and build a competitiveness network.

- Phase 3. Construct the IPCA plot and develop a product improvement strategy.
	
In the first phase, online reviews are classified as redesign, innovation, or noise. Specifically, using part-of-speech (POS) tagging, dependency relations analysis, mutual information (MI) searching, and affinity propagation (AP) clustering, redesign and innovation features are extracted from redesign and innovation reviews, respectively.
In the second phase, we can calculate the importance and performance of each feature using the SHAP method and sentiment analysis, and we determine each feature's competitiveness and competitiveness network using the proposed PUBG algorithm.
In the final phase, based on the obtained importance, performance, and competitiveness, the IPCA plot can be constructed. Then, using the importance, performance, competitiveness network, and proposed MSCS algorithm, we can develop the product improvement strategy.

![image.png](https://s2.loli.net/2023/11/04/Y78GHEVWCjBrmoN.png)

## Environment Requirements

To run the code, you will need to make sure that you have the following dependencies installed: 

`Python 3.6` `numpy` `tensorflow` `scikit-learn` `stanfordcorenlp` `networkx` `pandas` `gensim` `keras-xlnet`

## Replicating

The `src` folder contains all the code which implements the framework of this paper. Its structure is used when the provided software reads and writes files and references modules.

- Categorize online reviews as redesign, innovation, or noise: `./src/Review Category/`
- Extract product features: `./src/Review Feature Extraction/`
- Clustering of extracted features: `./src/Review Feature Clustering/`
- Calculating the importance, performance and competitiveness of product features: `./src/Calculate Feature Importance, Performance and Competitiveness/`
- Develop specific product improvement strategies using the MSCS algorithm: `./src/MSCS Algorithm/`

## Results

Figure 4 details how the IPCA plot generates insights into product improvement strategies.
<img width="700" alt="Results; Table 3" src="https://s2.loli.net/2023/11/04/IFh6KmaNOTEpAWR.png">

Figure 6 shows the IPCA plot of ten redesign and innovation features.
![image.png](https://s2.loli.net/2023/11/04/s5f6XZL2VgzlFtb.png)

Figure 10 shows the effect comparison of the different algorithms.
![image.png](https://s2.loli.net/2023/11/04/GVQ9gPRKmJXMLTO.png)

You can access more results from the original paper.

## Building

In Linux, to build the version that multiplies all elements of a vector by a
constant (used to obtain the results in [Figure 1](results/mult-test.png) in the
paper), stepping K elements at a time, execute the following commands.

```
make mult
```

Alternatively, to build the version that sums the elements of a vector (used
to obtain the results [Figure 2](results/sum-test.png) in the paper), stepping K
elements at a time, do the following.

```
make clean
make sum
```

Be sure to make clean before building a different version of the code.

## Results

Figure 1 in the paper shows the results of the multiplication test with different
values of K using `gcc` 7.5 on an Ubuntu Linux box.

![Figure 1](results/mult-test.png)

Figure 2 in the paper shows the results of the sum test with different
values of K using `gcc` 7.5 on an Ubuntu Linux box.

![Figure 1](results/sum-test.png)

## Replicating

To replicate the results in [Figure 1](results/mult-test), do either

```
make mult-test
```
or
```
python test.py mult
```
To replicate the results in [Figure 2](results/sum-test), do either

```
make sum-test
```
or
```
python test.py sum
```

## Ongoing Development

This code is being developed on an on-going basis at the author's
[Github site](https://github.com/tkralphs/JoCTemplate).

## Support

For support in using this software, submit an
[issue](https://github.com/tkralphs/JoCTemplate/issues/new).
