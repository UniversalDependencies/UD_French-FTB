# Summary
The Universal Dependency version of the French Treebank (Abeillé et al., 2003), hereafter UD_French-FTB, is a treebank of sentences from the newspaper Le Monde, initially manually annotated with morphological information and phrase-structure and then converted to the Universal Dependencies annotation scheme. 

# Introduction
This release of the French Treebank (Abeille et al, 2003) UD 2.1 version is based on the FTB SPMRL release (Seddah et al, 2O13)
whose tokenization has been changed to match the [UD 2.0 specifications](http://universaldependencies.org/u/overview/tokenization.html) . Its native depedency scheme was converted via the use of the [Sequoia treebank UD conversion rules](https://gitlab.inria.fr/grew/SSQ_UD) and a data-driven cross-treebank annotation transfer process (Seddah et al, 2017, forthcoming).

An evaluation on a gold standard leads to 94.75% of LAS, 99.40% UAS on the test set, on par with other high quality UD treebanks such as UD_English.


# Origin
The French Treebank annotation project has a long history of intermediate releases, culminating with [the official 1.0 version](http://ftb.linguist.univ-paris-diderot.fr/index.php?langue=en), available since January 2017.

For comparability reason with published parsing results, we derived the UD_French-FTB from the versions released for the SPMRL Shared Tasks (2013,2014).

Some notable versions have been used for research in  statistical parsing:
*2004: whole set of sentences used by Arun et al. 2005 , without any functional annotations ;
*2007: version with 12.531 sentences with functional annotations, used e.g. in Candito et al. 2010 ;
*2010: version with 15.922 sentences with functional annotations, used e.g. in Green et al., 2011 ;
*2013: version with 18.535 sentences with functional annotations, used for the SPMRL 2013 shared tasks (Seddah et al. 2013).

# Splitting
The whole corpus contains 18,535 sentences and 456,576 tokens.

In **UD_French-FTB**, the split follows the FTB SPMRL instance.
 * `fr_ftb-ud-test.conllu`: 61,287 tokens for 2541 sentences
 * `fr_ftb-ud-dev.conllu`: 318,818 tokens for 1235 sentences
 * `fr_ftb-ud-train.conllu`: 363,471 tokens for 14,759 sentences

Note that, the first 9981 sentences correspond to the canonical 2007 training set,  the last 1235 sentences of the test set to its 2007 counterpart and the dev set is the same.


# Genres
The original sentences of the corpus originate from the Le Monde newspaper (1990-1993), and cover various kind of newswire articles (sports, cinema, interviews, current affairs and financial news).


# Building the Treebank
The construction of the **UD_French-FTB** is described in this paper (Seddah et al, 2017, to appear).

# License
The French treebank is distributed freely for research purposes, provided you fill and return the licence
that can be found here : http://www.llf.cnrs.fr/Gens/Abeille/French-Treebank-fr.php.

Alternatively, the original FTB can be downloaded and an ID license number will be provided.
http://ftb.linguist.univ-paris-diderot.fr/telecharger.php?&langue=en

Pleae note that the UD annotation layers are released under the CC by-nc-sa 4.0 license.

# How to get the full data
Due to the FTB licensing restrictions (original data are under an LDC's license), the annotations are released without the lexical data. To merge the annotation with the corresponding FTB data, please follow the following steps:

- Obtain a copy of the FTB (either via the link above or via the SPMRL Shared Task data set license http://dokufarm.phil.hhu.de/spmrl2014/lib/exe/fetch.php?media=french.pdf)
- Send the ID license number or the signed license to djame.seddah@gmail.com 
- a diff file will be then made available for download
- uncompress and apply that patch inside the current UD_French-FTB directory (eg. patch -p1 < [patch file])


# Acknowledgments

contributors:
Marie Candito, Bruno Guillaume, Teresa Lynn, Hector Martinez-Alonso, Benoit Sagot, Djamé Seddah, Eric Villemonte de la Clergerie

contact: 
Djamé Seddah: djame.seddah@paris-sorbonne.fr  
Marie Candito: marie.candito@linguist.univ-paris-diderot.fr

# References
**(Abeillé et al., 2003)**  Anne Abeillé, Lionel Clément, and Françàçs Toussenel. 2003. "Building a treebank for French", in A. Abeillé (ed) Treebanks, Kluwer, Dordrecht. 

**(Arun et Keller. 2005)** Abhishek Arun and Frank Keller. 2005. Lexicalization in crosslinguistic probabilistic parsing: The case of French. In Proceedings of ACL, pages 306–313, Ann Arbor, MI.

**(Candito et al, 2010)** Marie Candito, Joakim Nivre, Pascal Denisand Enrique Henestroza Anguiano, 2010,  "Benchmarking of Statistical Dependency Parsers for French", Proceedings of COLING'2010, Beijing, China

**(Green et al, 2011)** Spence Green, Marie-Catherine de Marneffe, John Bauer J. and Christopher D. Manning. "2011. Multiword Expression Identification with Tree Substitution Grammars: A Parsing tour de force with French." In EMNLP 2011.

**(Seddah et al, 2O13)** Djamé Seddah, Reut Tsarfaty, Sandra Kübler, Marie Candito, Jinho D. Choi, Richárd Farkas, Jennifer Foster, Iakes Goenaga, Koldo Gojenola Galletebeitia, Yoav Goldberg, Spence Green, Nizar Habash, Marco Kuhlmann, Wolfgang Maier, Yuval Marton, Joakim Nivre, Adam Przepiórkowski, Ryan Roth, Wolfgang Seeker, Yannick Versley, Veronika Vincze, Marcin Woliski,Alina Wróblewska,Eric Villemonte de la Clergerie. 2013. "Overview of the SPMRL 2013 Shared Task: A Cross-Framework Evaluation of Parsing Morphologically Rich Languages" Proceedings of the Fourth SPMRL Workshop, Seattle, USA



# Changelog

* 2017-11-15 v2.1
  * Automatic application of new decisions taken for harmonisation of several French Treebanks (causative, copules, auxiliaries)
  A few modifications were applied to augment consistency with some of the other UD_French treebanks (main UD_French and UD_French-Sequoia):
  
  The possessive determiners attach now with a "det" dependency instead of "nmod:poss"
  
  Causative constructions now represent "faire" as an auxiliary.
  
  The causer argument bears a nsubj:caus label
  
  The only valid auxiliaries are "être", "avoir" and "faire" (a dozen unfixed cases remain though)
  
  The only valid copula is "être"
  
  Moreover, when the copula introduces an infinitival clause or a full clause, then "être" is not treated as a cop, but is taken to be the root.
  
  Examples:
  
      L'objectif est de calmer les esprits ==>  "est" is root, and "calmer" is its xcomp.
      
      Le plus étonnant est que la baisse accélère ==> "est" is root, and "accélère" is its ccomp
      
* 2017-03-08 v2.0
  * First release for inclusion as supplementary data for the ConLL 2017 Universal Dependency parsing shared task.


=== Machine-readable metadata (DO NOT REMOVE!) ================================
Data available since: UD v2.0
License: LGPL-LR
Includes text: no
Genre: newswire
Lemmas: converted from manual
UPOS: converted from manual
XPOS: not available
Features: converted from manual
Relations: converted from manual
Contributors: Candito, Marie; Guillaume, Bruno ; Lynn, Teresa ; Martinez-Alonso, Hector ; Sagotm Benoit ; Seddahm Djamé;  Villemonte de la Clergerie, Eric
Contributing: elsewhere
Contact: djame.seddah@paris-sorbonne.fr marie.candito@linguist.univ-paris-diderot.fr
===============================================================================