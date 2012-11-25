﻿Eutils-JSON
===========

Conversion XSLTs for NCBI [E-utilities](http://www.ncbi.nlm.nih.gov/books/NBK25501/) XML to JSON.

Please send us your feedback.

We are preparing to add JSON output format to NCBI E-utilities, and are making
this preliminary XSLT conversion available in order to solicit community feedback.

Please submit pull requests, create a github issue here, or send an email to
[eutilities@ncbi.nlm.nih.gov](mailto:eutilities@ncbi.nlm.nih.gov).

_We will implement this very soon, so send us feedback as soon as possible (preferably
by the end of November, 2012)._


##Samples

You can just use xsltproc to try these out.  For example,

    xsltproc Eutils2JSON.xsl http://eutils.ncbi.nlm.nih.gov/entrez/eutils/einfo.fcgi

### [Einfo](http://www.ncbi.nlm.nih.gov/books/NBK25499/#chapter4.EInfo)

#### ✓ EInfo - list all databases

http://eutils.ncbi.nlm.nih.gov/entrez/eutils/einfo.fcgi

([einfo.xml](klortho/samples/einfo.xml)),
([einfo.json](klortho/samples/einfo.json)),

#### ✓ EInfo about PubMed

http://eutils.ncbi.nlm.nih.gov/entrez/eutils/einfo.fcgi?db=pubmed

([einfo.pubmed.xml](klortho/samples/einfo.pubmed.xml)),
([einfo.pubmed.json](klortho/samples/einfo.pubmed.json)),

#### ✓ EInfo error

http://eutils.ncbi.nlm.nih.gov/entrez/eutils/einfo.fcgi?db=fleegle

([einfo.error.xml](klortho/samples/einfo.error.xml)),
([einfo.error.json](klortho/samples/einfo.error.json)),


### [Esummary version 2.0](http://www.ncbi.nlm.nih.gov/books/NBK25499/#chapter4.ESummary)

#### ✓ PubMed - version 2.0

http://eutils.ncbi.nlm.nih.gov/entrez/eutils/esummary.fcgi?db=pubmed&id=5683731,22144687&retmode=xml&version=2.0

([esummary.pubmed.xml](klortho/samples/esummary.pubmed.xml)),
([esummary.pubmed.json](klortho/samples/esummary.pubmed.json)),

#### ✓ Unists - version 2.0

http://eutils.ncbi.nlm.nih.gov/entrez/eutils/esummary.fcgi?db=unists&id=254085,254086&version=2.0

([esummary.unists.xml](klortho/samples/esummary.unists.xml)),
([esummary.unists.json](klortho/samples/esummary.unists.json)),



### [Esummary version 1](http://www.ncbi.nlm.nih.gov/books/NBK25499/#chapter4.ESummary)

(These maybe won't be used.)

#### ✓ PubMed - version 1

http://eutils.ncbi.nlm.nih.gov/entrez/eutils/esummary.fcgi?db=pubmed&id=5683731,22144687&retmode=xml

([esummary.pubmed.1.xml](klortho/samples/esummary.pubmed.1.xml)),
([esummary.pubmed.1.json](klortho/samples/esummary.pubmed.1.json)),

#### ✓ Unists - version 1

http://eutils.ncbi.nlm.nih.gov/entrez/eutils/esummary.fcgi?db=unists&id=254085,254086

([esummary.unists.1.xml](klortho/samples/esummary.unists.1.xml)),
([esummary.unists.1.json](klortho/samples/esummary.unists.1.json)),



##Changes from master branch

* Added 'version'
* Removed the redundant "name" field inside child hashes.  Maybe should keep it,
instead -- it doesn't do any harm, and could conceivably be useful.
* Changed esummary 1.0 docsums to be a hash, and the id field of each docsum is the key.
* Further changed some of the structure of esummary 1.0 output.
* Prettified the output.  This can be turned off by passing in the "pretty" parameter is
false.

##Questions

* What is the str:decode-uri() doing in the np:q function?  Are some of these values
really URI-style percent encoded?

##To do

* Esummary output should be based on version 2.0 XML, not 1.0.

##Authors

Mark Johnson, Chris Maloney