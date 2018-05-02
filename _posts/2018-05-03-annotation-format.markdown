---
layout: post
title:  "New HPO Annotation File Format"
date:   2018-05-02 05:00:00
categories: 
---

## New HPO Annotation File Format
The HPO project is transition to a new annotation file format in 2018, and we are requesting comments, suggestions, and other feedback prior to making the switch.
The current annotation format dates back to the early days of the HPO project in 2009 and needed some minor improvements to be able to capture more metadata about the phenotypic abnormalities that characterize disease. 
The 2009-present format is described here: http://human-phenotype-ontology.github.io/documentation.html#annot
The new 2018-onwards format is described here: 
http://hpo-annotation-qc.readthedocs.io/en/latest/annotationFormat.html#new-and-old-big-file-formats

The main differences are

1. The frequency field is now strictly constrained to have one of three formats: HP:0003577 (a term from the frequency subontology) or 12/45 or 22% 
2. There is a field that can indicate sex-limited phenotypes
3. There is a field that can be used to record terms from the HPO ClLinical modifier subontology (e.g., “bilateral” or “transient”)
4. The Aspect field has been updated to reflect the fact that annotations can come out of the subontologies Phenotypic abnormality, Inheritance, Clinical course, or Clinical Modifier.

The new annotation file  is located on our [Hudson server](http://compbio.charite.de/jenkins/job/hpo.annotations.2018/) and is called phenotype.hpoa.

Feedback on the format is welcome. We also welcome feedback on the question whether the practice of having a separate file for negative (“NOT”) phenotype annotations should be maintained, \since we are considering putting all information in one file (the negative lines have a NOT in column 4 in both new and old formats).

Please contact peter.robinson@jax.org with questions or comments.


