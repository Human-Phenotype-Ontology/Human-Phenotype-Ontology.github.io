---
layout: page
title: FAQ
sitemap:
    priority: 1.0
    changefreq: weekly
    lastmod: 2015-09-24T16:31:30+05:30
---


##  How to collaborate with the HPO ?

 
We welcome the participation of interested colleagues. We anticipate that the structure of the HPO will continue to be refined and completed for some time to come. Groups or persons with expert knowledge in a particular domain of human phenotyping in a medical genetics setting are invited to contribute their knowledge on a collaborative basis. Please contact Peter Robinson or Sebastian Köhler to discuss details.
 
We are currently transitioning from annotations dervied in a semiautomated fashion from the OMIM database to curated annotations. Given the number of human hereditary diseases, this is no small task. We greet participation of colleagues with an interest in specific hereditary diseases to improve the annotations for 'their' disease. Please get in contact with us (Peter Robinson or Sebastian Köhler) to discuss this form of collaboration. We are also preparing an online form for manual annotations.
 
The issue tracker is [available on Github](https://github.com/obophenotype/human-phenotype-ontology/issues).


## What is the difference between *genes\_to\_phenotypes.txt* and *phenotype\_to\_genes.txt* ?

A question that is asked very often, deals with the asymmetriy of the files:

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

