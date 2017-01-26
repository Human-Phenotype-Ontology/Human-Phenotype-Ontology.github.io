---
layout: page
title: Documentation
sitemap:
    priority: 1.0
    changefreq: weekly
    lastmod: 2015-09-24T16:31:30+05:30
---

This page is split into:

 - [Introduction](#intro)
 - [Annotation guide](#annot)
 - [Logical definitions](#defs)



## <a name="intro"></a> An Introduction to the Human Phenotype Ontology 


The Human Phenotype Ontology (HPO) intends to offer a tool that will allow large-scale computational analysis of the human phenome. The HPO currently contains over 11,000 terms, each of which describes an individual phenotypic anomaly. The terms are arranged in a directed acyclic graph and are connected by **is-a** (subclass-of) edges, such that a term represents a more specific or limited instance of its parent term(s). All relationships in the HPO are **is-a** relationships, i.e. simple class-subclass relationships. For instance, *Abnormality of the feet* **is-a** *Abnormality of the lower limbs*. The relationships are transitive, meaning that they are inherited up all paths to the root. [*Phenotypic abnormality*](http://www.human-phenotype-ontology.org/hpoweb?id=HP:0000118) is the main subontology of the HPO and contains descriptions of clinical abnormalities. Additional subontologies are provided to describe inheritance patterns, onset/clinical course and modifiers of abnormalities.

*What is An Ontology and What Use is An Ontology for Medical Genetics Research?*

The word ontology is derived from Greek words meaning the study of existance and being. More recently, the word ontology has been used in computer science to describe systems that describe concepts within some domain and relationships between those concepts. The Gene Ontology consortium has developed an extensive ontology describing molecular functions, biological processes, and cellular locations over the last decade and a number of groups have supplied annotations using the GO terms to gene products of many organisms. The study of human phenotypes in the context of hereditary and common disease has the potential to lead to great insight on the function of genes and genetic networks. The HPO intends to offer such a computational tool that will allow large-scale computational analysis of the human phenome.

*What is the Medical Focus of the Human Phenotype Ontology?*

Currently, the most useful and comprehensive database of human hereditary disorders is the Online Mendelian Inheritance in Man (OMIM) database. OMIM contains clinical data on several thousand primarily monogenic hereditary disorders. Since OMIM and its predecesor Mendelian Inheritance in Man (McKusick) were initially developed over 30 years ago, OMIM did not use a controlled vocabulary to describe clinical features, and uses a more or less simple hierarchical scheme to assign clinical features to organ systems. Despite these drawbacks, OMIM was and will continue to be an incredibly useful resource for clinicians and researchers. We have therefore mapped nearly all clinical descriptions in OMIM to terms of the HPO. We have embedded these mappings into an ontological, multi-tiered structure that is described below and intend to continue refining and improving the HPO. We have also annotated all Orphanet entries and over 60 recurrent syndromes in DECIPHER.
 
*Terms in the Human Phenotype Ontology*

Each term in the HPO describes a clinical abnormality. These may be general terms, such as *Abnormality of the musculoskeletal system* or very specific such as *Chorioretinal atrophy*. Each term is also assigned to one of the four ontologies, *Phenotypic abnormality*, *Clinical modifier*, *Mortality/Aging* or *Mode of inheritance*. Most of the terms of the HPO belong to the *Phenotypic abnormality* ontology. The terms have a unique ID such as *HP:0001140* and a label such as *Epibulbar dermoids*.  Most terms have textual definitions such as *An epibulbar dermoid is a benign tumor typically found at the junction of the cornea and sclera (limbal epibullar dermoid).* The source of the definition must be indicated. Many terms have synonyms. For instance, *Epibulbar dermoid* is taken to be a synonym of *Epibulbar dermoids*.


|---
| Subontology | Description |
|:-|:-|:-:
| [*Phenotypic abnormality*](http://www.human-phenotype-ontology.org/hpoweb?id=HP:0000118)  | This is the main ontology of the HPO and contains descriptions of clinical abnormalities. The level 1 children of this class are formed by terms such as *Abnormality of the musculoskeletal system* and *Hematological abnormality*.
| [*Mode of Inheritance*](http://www.human-phenotype-ontology.org/hpoweb?id=HP:0000005)  | This relatively small ontology is intended to describe the mode of inheritance and contains terms such as *Autosomal dominant*..
| [*Clinical modifier*](http://www.human-phenotype-ontology.org/hpoweb?id=HP:0012823)  | This ontology contains classes that describe typical modifiers of clinical symptoms. For example the speed of progression, the variablity or the onset. It contains terms such as *Onset in childhood*, *Rapidly progressive*, or *Incomplete penetrance*.
| [*Mortality/Aging*](http://www.human-phenotype-ontology.org/hpoweb?id=HP:0040006)  | This sub-ontology describes *Time of death* and contains classes such as *Neonatal death* or *Sudden death*.
| [*Frequency*](http://www.human-phenotype-ontology.org/hpoweb?id=HP:0040279)  | Frequency with that patients do show a particular clinical feature. Examples are *Obligate*, *Frequent*, and *Occasional*. These terms are defined in the same way as Orphanet defines them.


*The Structure of the Human Phenotype Ontology*

Most ontologies are structured as directed acyclic graphs (DAG), which are similar to hierarchies but differ in that a more specialized term (child) can be related to more than one less specialized term (parent).  Cycles (cyclic paths in the graph) are not allowed. The relationship of the terms of the HPO to one another is displayed in the DAG. For instance, the term *Aplasia/Hypoplasia of metatarsal bones* is a child of both *Aplasia/Hypoplasia involving bones of the feet* and *Abnormalities of the metatarsal bones*. The ability to encode multiple parents in a DAG adds to the flexibility and descriptiveness of the ontology. For instance, it is possible to search for all terms involving *Aplasia/Hypoplasia of the skeleton* as well as to search for all terms involving *Abnormalities of the foot*. This would not be possible with a simple hierarchical system.
The **is-a** relationship is transitive, meaning that annotations are inherited up all paths to the root. For instance, 
*Abnormality of the lower limbs* **is-a** *Abnormality of the extremities*, and thus *Abnormality of the feet* also **is-a** *Abnormality of the extremities*.




## <a name="annot"></a> Annotation guide / File format

We represent clinical annotations using a simple tab-delimited format that was designed to be as similar as possible to the format used by the Gene Ontology consortium. 
This document describes the process of assigning HPO terms to disease entities such as Mendelian disorders from OMIM or Orphanet. Each line in the annotation file represents a 
link between a disease entity such as *Noonan syndrome* and one of the clinical features characteristically seen in that disease. Each of the features of a disease is to be listed on a separate line.
Note that this file (and format) is intended to be used for the annotation of disease entities (e.g. *Noonan syndrome*) and not individuals (such as a person that has been diagnosed with *Noonan syndrome*). 
You may have look at [PhenoTips](https://phenotips.org/) if you are aiming at annotating clinical findings of individuals with hereditary diseases. 

*The flat file format comprises 14 tab-delimited fields*

|---
|Column|Content|Required|Example
|---
1 | DB | required | MIM
2 | DB_Object_ID | required | 154700
3 | DB_Name | required | Achondrogenesis, type IB
4 | Qualifier | optional | NOT
5 | HPO ID | required | HP:0002487
6 | DB:Reference | required | OMIM:154700 or PMID:15517394
7 | Evidence code | required | IEA
8 | Onset modifier | optional | HP:0003577
9 | Frequency modifier | optional | Usually from the subontology [*Frequency*](http://www.human-phenotype-ontology.org/hpoweb?id=HP:0040279) or "70%" or "12 of 30"
10 | With | optional |  
11 | Aspect | required | O
12 | Synonym | optional | ACG1B\|Achondrogenesis, Fraccaro type
13 | Date | required | YYYY.MM.DD
14 | Assigned by | required | HPO
|---


 1. **DB**: This field refers to the database from which the identifier in DB_Object_ID (column 2) is drawn. At present, only annotations from the OMIM database are available, but we are planning to add annotations to chromosomal disorders.
 2. **DB_Object_ID**: This is the identified of the annotated disease within the database indicated in column 1. Note that for OMIM identifiers, the symbol preceding the MIM number is omitted (*,#,+,%).
 3. **DB_Name**: This is the name of the disease associated with the DB_Object_ID in the database. Only the accepted name should be used, synonyms should not be listed here.
 4. **Qualifier**: This optional field can be used to qualify the annotation shown in *field 5*. Possible values of this field are **NOT**, **SECONDARY**, **MILD**,**MODERATE**,**SEVERE**. If multiple qualifiers are shown, they are separated by a comma (",") symbol. The meaning of individual modifiers is as follows:
   * NOT: The disorder being annotated is NOT characterized by the feature associated with HPO_ID in column 5. Note that annotations with the NOT modifier are moved to separate file!
   * SECONDARY: The feature is a secondary consequence of a primary pathophysiological event in another organ. For instance, although Jaundice is observed in the skin or sclerae, it is secondary to abnormalities in other organs. For instance, to indicate that jaundice seen in a certain disease is secondary to Cholestatic liver disease, we would annotate SECONDARY(HP:0002611), where HP:0002611 is the HPO identified of the term Cholestatic liver disease.
   * MILD, MODERATE, SEVERE, CHRONIC, PROGRESSIVE, NONPROGRESSIVE, EPISODIC, RECURRENT, PROFOUND, BILATERAL, DISTAL, GENERALIZED, PROXIMAL, REFRACTORY: In general, it is preferred to annotate with a term describing the underlying abnormality, such as Hearing loss, and to use qualifiers such as MILD, MODERATE, SEVERE if thought necessary to describe the severity of the clinical involvement. This is preferred because of the assumption that mild and moderate manifestations of specific medical abnormalities result from mild or moderate disturbances of the same cellular and physiological networks and also because distinctions that are often heard in clinical practice such as "mild-to-moderate" or grade "II-III/VI" often seem more or less arbitrary. It is an error to use more than one of the qualifiers MILD, MODERATE, SEVERE, etc. in one annotation.
It is expected that software does not depend on the qualifiers being listed in a certain order. Note that Frequency information is available in Column 9.
 
 5. **HPO ID**: This field is for the HPO identifier for the term attributed to the DB_Object_ID. This field is mandatory, cardinality 1.
 6. **DB:Reference**: This required field indicates the source of the information used for the annotation. This may be the clinical experience of the annotator or may be taken from an article as indicated by a pubmed id. Each collaborating center of the Human Phenotype Ontology consortium is assigned a HPO:Ref id. In addition, if appropriate, a pubmed id for an article describing the clinical abnormality may be used.
 7. **Evidence code**: This required field indicates the level of evidence supporting the annotation. At the kickoff of the HPO, most annotations were extracted by parsing the Clinical Features sections of the omim.txt file. These annotations are assigned the evidence code "IEA" (inferred from electronic annotation). Other codes include "PCS" for published clinical study. This should be used for information extracted from articles in the medical literature. Generally, annotations of this type will include the pubmed id of the published study in the DB:Reference field. Finally, "ICE" can be used for annotations based on individual clinical experience. This may be appropriate for disorders with a limited amount of published data. This must be accompanied by an entry in the DB:Reference field denoting the individual or center performing the annotation together with an identifier. For instance, GH:007 might be used to refer to the seventh such annotation made by a specialist from Gotham Hospital. (assuming the prefix GH has been registered with the HPO). We have also included "ITM" to mark annotations retrieved by text-mining (inferred by text-mining). Finally we have TAS, which stands for "traceable author statement", usually reviews or disease entries (e.g. OMIM) that only refers to the original publication.
 8. **Onset modifier**: A term-id from the HPO-sub-ontology below the term "Age of onset" (HP:0003674).
 9. **Frequency modifier**: A term-id from the HPO-sub-ontology below the term "Frequency" (HP:0040279). (since December 2016 ; before was a mixture of values). The terms for frequency are in alignment with Orphanet.
 10. **With**: This field is not currently used. However, it can be used to enter information about characteristics that go with the remaining annotation. For instance, in order to annotate a co-occurence of two features in some disease, one could add the qualified COOCCURS(17/18) and the identifier of some other characteristic in the WITH field to denote that the HPO term listed in the HPO ID field occurred in 17 of 18 cases of the disease listed in the DB_Object_ID field. In the future, the meaning of this field may be extended to include other information such as (for instance) repeat length in order to correlate, say, average age of onset of symptoms in Huntington disease with the number of CAG repeats in the huntingtin gene.
 11. **Aspect**: one of O (Phenotypic abnormality), I (inheritance), C (onset and clinical course) or M (Mortality/Aging). This field is mandatory; cardinality 1
 12. **Synonym**: This optional field can be used for a common abbreviation for the disease referred to by the *DB_Object_ID* such as "NF1" for neurofibromatosis type 1 or "MFS" for Marfan syndrome. It can also be used to store alternate names for a disorder. Individual synonyms should be separated by a pipe("\|") symbol.
 13. **Date**: Date on which the annotation was made; format is YYYY.MM.DD this field is mandatory, cardinality 1
 14. **Assigned by**: This refers to the center or user making the annotation.



## <a name="defs"></a> Computable Definitions of HPO Terms

Unless we instruct the computer otherwise, there is no implication that an HPO term such as *Cerebral calcification* is somehow related to the *human brain*. The HPO term can be related to other terms in the ontology by subclass relations, but it is not explicitly related to concepts from anatomy, histology, pathology, biochemistry, and cellular physiology. For this reason, a consortium including Sandra Dölken, Sebastian Köhler, and Peter N Robinson from the Institute of Human Genetics and Medical Genetics of the Charité Berlin, Chris Mungall and Suzi Lewis from the Berkely Bioinformatics Open Source Projects group, Barbara Ruef and Monte Westerfield from the Zebrafish Model Organism Database (ZFIN), and Melissa Haendel, Nicole Vasilevsky and Mark Engelstad from the Oregon Health & Science University has joined forces to develop computer-readable logical definitions of HPO terms that will allow human phenotypic abnormalities to be related to entities from anatomy, pathology, physiology, biochemistry, and other areas.

We are creating the definitions using the [Phenotypic Quality Ontology (PATO)](http://obofoundry.org/wiki/index.php/PATO:Main_Page). We logically define phenotypes by stating that classes in the HPO are logically equivalent to Entity/Quality descriptions, with each such description consisting of the following elements: Q, the type of quality (characteristic) that the genotype affects; E, the type of entity that bears the quality; E2, an additional optional entity type, for relational qualities; M, a modifier. The basic methodology has been described [in this paper](http://f1000research.com/articles/2-30/v2).








<!-- 
9. **Frequency modifier**: A percentage value reflecting the frequency with that the particular abnormality occurs in patients having the syndrome. Another possibility is to specifiy the number n of patients that have this feature out of the m patients investigated (n of m) If exact data are not available, categories from the following table may also be used for indicating the frequency of a phenotypic feature. As a rough guide, the HPO consortium interprets the following categories as having roughly the following numerical meaning (Table 2). 
   
    |---
    |Description|Percent of patients |
    |---
    very rare | 1 %
    rare | 5 %
    occasional | 7.5 %
    frequent | 33 %
    typical  | 50 % 
    variable | ? (prob. 30%-70%)
    common | 75 %
    hallmark  | 90 %
    obligate  | 100 % 
 
 -->

