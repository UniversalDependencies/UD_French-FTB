UD2 release of the French Treebank (v0.9.6) 
----------------------------------


This release of the French Treebank (Abeille et al, 2003) UD2 version is based on the FTB SPMRL release (Seddah et al, 2O13)
whose tokenization has been changed to match the UD 2.0 specifications [1] and on the use of Sequoia treebank  
UD conversion rules (Guillaume et al, forthcoming). These rules were applied "as it" and led to many conversion errors. We automatically corrected incorrect coordination tree structures and tagged wrong or missing errors POS using an updated version of the MElt tagger (Sagot, forthcoming). The tagger was trained on  90% of the Sequoia treebank and on the FTB training sentences that contain no conversion errors. This updated training set was then enriched with gold features extracted and synchronized from the FTB SPMRL version in order to be used as a training set for the DyaLog-SR parser (de la Clergerie, 2013).
Before automatic tree correction and pos tags reinjection, around 6% and 7% of tokens contained an error (pos, label, or missing head).

In order to evaluate the accuracy of our model we used pseudo gold trees structures (sentences with no conversion errors, pos tags corrected, ..) from the data set split , a sample of the Sequoia UD2 treebank and a manually validated small set from the FTB dev section (>30 sent. with initial conversion errors).

-----------------------------------------------------
Conversion accuracy against manual gold standard  : 
			(%)	LAS	UAS	LaS
initial Sequoia's set rules: 	86.39	89.29 	90.73
FTB UD2 "conversion system":	87.50	90.82	91.75

Conversion accuracy against pseudo-gold test set:
ftb train  (no fail):		98.60
ftb test (no fail):		98.64
ftb dev  (no fail):		98.49

Conversion accuracy against Gold Sequoia test set:
Sequoia gold:			98.50						
----------------------------------------------------

For reasons of consistency, we provide the result of the full-parsing conversion and not mix rule-based converted trees and parsed ones. 


The resulting data set is of course prone to corrections and is to be updated very soon (especially regarding some remaining errors in the label sets).


[1] http://universaldependencies.org/u/overview/tokenization.html

Note on the Multi-word Expressions:
----------------------------------
The FTB is currently under an intense scrutiny regarding its treatment of mwes, nominal ones are currently unchanged.
All the others have been regularized to match the UD2 scheme.

Statistics
----------

		sent.	tokens
train	14759	363471	
dev		1235	31818
test	2541	61287


License
-------
The French treebank is distributed freely for research purposes, provided you fill and return the licence
that can be found here : http://www.llf.cnrs.fr/Gens/Abeille/French-Treebank-fr.php.

Alternatively, the original FTB can be downloaded and an ID license number will be provided.
http://ftb.linguist.univ-paris-diderot.fr/telecharger.php?&langue=en

Pleae note that the UD annotation layer are released under the CC by-nc-sa 4.0 license.

DATA
----
Due to the FTB licensing restrictions (original data are under an LDC's license), the annotations are released without the data. To merge the annotation with the corresponding FTB data, please follow the following steps:

- Obtain a copy of the FTB (either via the link above or via the SPMRL Shared Task data set license http://dokufarm.phil.hhu.de/spmrl2014/lib/exe/fetch.php?media=french.pdf)
- Send the ID license number or the signed license to djame.seddah@gmail.com 
- a diff file will be then made available for download
- uncompress and apply that patch inside the current UD_French-FTB directory (eg. patch -p1 < [patch file])


Fixes
-------

Please contact Djamé Seddah or Marie Candito for any errors, bugs or remarks you may have on this version.

Website
--------
tbd


Contributors
------------
Marie Candito, Bruno Guillaume, Teresa Lynn, Hector Martinez-Alonso, Benoit Sagot, Djamé Seddah, Eric de la Clergerie


Contacts
---------
djame.seddah@paris-sorbonne.fr
marie.candito@linguist.univ-paris-diderot.fr

=== Machine-readable metadata (DO NOT REMOVE!) ================================
Documentation status: stub
Data source: automatic
Data available since: UD v2.1
License: CC BY-NC-SA 4.0
Genre: nonfiction news
Contributors: Candito, Marie; Guillaume, Bruno; Lynn, Teresa; Martínez Alonso, Héctor; Sagot, Benoit; Seddah, Djamé; de la Clergerie, Eric
Contact: djame.seddah@paris-sorbonne.fr, marie.candito@linguist.univ-paris-diderot.fr
===============================================================================
