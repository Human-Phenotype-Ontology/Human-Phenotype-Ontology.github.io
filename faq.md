---
layout: page
title: FAQ
sitemap:
    priority: 1.0
    changefreq: weekly
    lastmod: 2015-09-24T16:31:30+05:30
---


##  How to collaborate with the HPO ?

 
We welcome the participation of interested colleagues. We anticipate that the structure of the HPO will continue to be refined and completed for some time to come. Groups or persons with expert knowledge in a particular domain of human phenotyping in a medical genetics setting are invited to contribute their knowledge on a collaborative basis. Please [contact us](contact.html) to discuss details.
 
We are currently transitioning from annotations derived in a semiautomated fashion from the OMIM database to manually curated annotations. Given the number of human hereditary diseases, this is no small task. We greet participation of colleagues with an interest in specific hereditary diseases to improve the annotations for 'their' disease. Please get in [contact with us](contact.html) to discuss this form of collaboration. We are also preparing an online system for manual annotations.
 
The issue tracker is [available on Github](https://github.com/obophenotype/human-phenotype-ontology/issues).

#### Collaborations for translations
We are working with several people to translate more content of HPO into a multitude of languages. Several translations are being actively developed at the moment (e.g. german).

The translations are considered a project coordinated by the HPO team and is hosted [on GitHub](https://github.com/Human-Phenotype-Ontology/HPO-translations). 
Please do not start translating HPO content without contacting us beforehand. This might cause duplicated translations and other problems. Please [contact us here](contact.html).


## What is the difference between *genes\_to\_phenotypes.txt* and *phenotype\_to\_genes.txt* ?

A question that is asked very often, deals with the asymmetry of the files:

 - *genes\_to\_phenotypes.txt* 
 - *phenotype\_to\_genes.txt*
 
The difference is that one files uses the transitivity of the annotations and the other does not. I.e. in *genes\_to\_phenotypes.txt*  we list for each gene the most specific HPO-classes (and not all the ancestors). 
In *phenotype\_to\_genes.txt* we show each phenotype that has at least one gene associated with it. Additionally, we have mapped the genes to all its the ancestor classes. 
For example given that: 
 
 - *HP_1* subclass_of *HP_3*
 - *HP_2* subclass_of *HP_3* 

and *genes\_to\_phenotypes.txt* contains

 -  **geneA** annotated to *HP_1*
 -  **geneB** annotated to *HP_2*

then *phenotype\_to\_genes.txt* contains: 

 - *HP_3* annotates  **geneA** and **geneB** 


## What is the difference between "ALL_FREQUENCIES" and "FREQUENT_FEATURES"?

Each annotation has a frequency associated, i.e. how many patients with that disease have this clinical feature. “ALL_FREQUENCIES” denotes that we do not use any filter. “FREQUENT_FEATURES” means that we exclude all features seen in less than 50% of the patients.



## What is your procedure for associating genes with HPO phenotypes?
The following file is used to associate genes with phenotypes.

 - *genes\_to\_phenotypes.txt*

In many cases, there are multiple diseases that are associated with mutations in the same gene (for instance, mutations in the LMNA gene are associated with multiple diseases including
Cardiomyopathy, dilated, 1A [MIM:115200], Charcot-Marie-Tooth disease, type 2B1 [605588], Emery-Dreifuss muscular dystrophy 2, AD [181350], and Hutchinson-Gilford progeria [176670]. Each
of these diseases is associated with a different spectrum of phenotypic features. The gene-to-phenotype association in our databases takes the set of all phenotypic features (HPO terms)
associated with one or more diseases causes by mutation in the gene under consideration. Thus, LMNA is associated with Alopecia (which is a feature of Hutchinson-Gilford progeria) as
well as Ventricular arrhythmia (which is a feature of Cardiomyopathy, dilated, 1A). 
