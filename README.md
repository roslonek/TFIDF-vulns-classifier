# TFIDF-vulns-classifier

This repo hosts a tool for automatic (unsupervised) calssification of CVEs based on LDA/TF-IDF technique used against Synopsis field in order to help in quicker analysis of large sets of found CVEs.
Input for script is Nessus CSV format of scan as a training and test data, other required parmeter contains a mapping file that attaches own Labels for proposed by LDA categories (regex based).

Background:
TF-IDF (term frequency-inverse document frequency) is a feature engineering technique where the most important words are extracted by taking into account their frequency in documents and across the entire list of documents as a whole.

Topic modeling is an unsupervised learning method where groups of words that often appear together are clustered into topics. Typically, the words in one topic should be related and make sense (e.g in our case Java CVEs or OpenSSL topics). Individual documents (CVEs) can fall under one topic or multiple topics.

In natural language processing, the latent Dirichlet allocation (LDA) is a generative statistical (topic modeling) model that allows sets of observations to be explained by unobserved groups that explain why some parts of the data are similar.

According to LDA (LatentDirichletAllocation) every word is associated (or related) with a latent (or hidden) topic.
in proposed algorithm LDA is used to analyse list of found CVEs and words from each CVE Synopsis field (out of Nessus format)  to train model with possible distinct number of categories -  20 as default and deriving from there a way to map huge number of CVEs into small number of classes.

In LDA, documents (here each CVEs Synopsis field) are considered to be bags of words and words are considered to be independent given the topics (i.e., word order is irrelevant). When LDA is run, the various distributions are learned using Bayesian inference. In effect, the generative model just described is run backwards and the distributions are updated from their priors using the actual documents


