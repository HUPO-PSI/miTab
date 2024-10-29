# PSI-MI TAB 2.6 Format #

## Introduction ##

The MITAB26 format is part of the PSI-MI 2.5 standard (1). It has been derived from the tabular format provided by BioGrid. MITAB26 only describes binary interactions, one pair of interactors per row. Columns are separated by tabulations. Tools allowing to manipulate this data format are available (2).

(1) http://www.pubmedcentral.nih.gov/articlerender.fcgi?tool=pubmed&pubmedid=17925023

(2) http://www.psidev.info/groups/molecular-interactions (Tools section)


## Column definitions ##

The column contents should be as follows:

  1. **Unique identifier for interactor A**, represented as databaseName:ac, where     databaseName is the name of the corresponding database as defined in the [PSI-MI controlled vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0444), and ac is the unique primary identifier of the molecule in the database. Identifiers from multiple databases can be separated by "|". It is recommended that proteins be identified by stable identifiers such as their UniProtKB or RefSeq accession number.
  1. **Unique identifier for interactor B**.
  1. **Alternative identifier for interactor A**, for example the official gene symbol as defined by a recognised nomenclature committee. Representation as databaseName:identifier. Multiple identifiers separated by "|".
  1. **Alternative identifier for interactor B**.
  1. **Aliases for A**, separated by "|". Representation as databaseName:identifier. Multiple identifiers separated by "|".
  1. **Aliases for B**.
  1. **Interaction detection methods**, taken from the corresponding [PSI-MI controlled Vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0001), and represented as darabaseName:identifier(methodName), separated by "|".
  1. **First author** surname(s) of the publication(s) in which this interaction has been shown, optionally followed by additional indicators, e.g. "Doe-2005-a". Separated by "|".
  1. **Identifier of the publication** in which this interaction has been shown. Database name taken from the [PSI-MI controlled vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0445), represented as databaseName:identifier. Multiple identifiers separated by "|".
  1. **NCBI Taxonomy identifier for interactor A**. Database name for NCBI taxid taken from the [PSI-MI controlled vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0444), represented as databaseName:identifier (typicaly databaseName is set to 'taxid'). Multiple identifiers separated by "|". Note: In this column, the databaseName:identifier(speciesName) notation is only there for consistency. Currently no taxonomy identifiers other than NCBI taxid are anticipated, apart from the use of -1 to indicate "in vitro", -2 to indicate "chemical synthesis", -3 indicates "unknown", -4 indicates "in vivo" and -5 indicates "in silico".
  1. **NCBI Taxonomy identifier for interactor B**.
  1. **Interaction types**, taken from the corresponding [PSI-MI controlled vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0190), and represented as dataBaseName:identifier(interactionType), separated by "|".
  1. **Source databases** and identifiers, taken from the corresponding [PSI-MI controlled vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0444), and represented as databaseName:identifier(sourceName). Multiple source databases can be separated by "|".
  1. **Interaction identifier(s)** in the corresponding source database, represented by databaseName:identifier
  1. **Confidence score**. Denoted as scoreType:value. There are many different types of confidence score, but so far no controlled vocabulary. Thus the only current recommendation is to use score types consistently within one source. Multiple scores separated by "|".
  1. **Expansion**. Model used to convert n-ary interactions into binary interactions for purpose of export in MITAB file. The known expansions are none (if true binary interaction), spoke, matrix or bipartite.
  1. **Biological role A** , taken from the corresponding [PSI-MI controlled Vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0500), and represented as dataBaseName:identifier(biological role name), separated by "|".
  1. **Biological role B** , taken from the corresponding [PSI-MI controlled Vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0500), and represented as dataBaseName:identifier(biological role name), separated by "|".
  1. **Experimental role A** , taken from the corresponding [PSI-MI controlled Vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0495), and represented as dataBaseName:identifier(experimental role name), separated by "|".
  1. **Experimental role B** , taken from the corresponding [PSI-MI controlled Vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0495), and represented as dataBaseName:identifier(experimental role name), separated by "|".
  1. **Interactor type A** , taken from the corresponding [PSI-MI controlled Vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0313), and represented as dataBaseName:identifier(interactor type name), separated by "|".
  1. **Interactor type B** , taken from the corresponding [PSI-MI controlled Vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0313), and represented as dataBaseName:identifier(interactor type name), separated by "|".
  1. **Xref for interactor A**, for example the gene ontology cross references associated. Representation as databaseName:identifier(text). Multiple cross references separated by "|".
  1. **Xref for interactor B**, for example the gene ontology cross references associated. Representation as databaseName:identifier(text). Multiple cross references separated by "|".
  1. **Xref for the interaction**, for example the gene ontology cross references associated (components, etc.) or OMIM cross references. Representation as databaseName:identifier(text). Multiple cross references separated by "|".
  1. **Annotations for interactor A**, for example comments about this interactor. Representation as topic:text. Multiple annotations separated by "|".
  1. **Annotations for Interactor B**, for example comments about this interactor. Representation as databaseName:identifier(text). Multiple annotations separated by "|".
  1. **Annotations for the interaction**, for example comments about this interaction. Representation as topic:text. Multiple annotations separated by "|".
  1. **NCBI Taxonomy identifier for the host organism**. Database name for NCBI taxid taken from the [PSI-MI controlled vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0444), represented as databaseName:identifier (typicaly databaseName is set to 'taxid'). Multiple identifiers separated by "|". Note: In this column, the databaseName:identifier(speciesName) notation is only there for consistency. Currently no taxonomy identifiers other than NCBI taxid are anticipated, apart from the use of -1 to indicate "in vitro", -2 to indicate "chemical synthesis", -3 indicates "unknown", -4 indicates "in vivo" and -5 indicates "in silico".
  1. **Parameters of the interaction**, for example kinetics. Representation as type:value(text). The type can be taken from the corresponding [PSI-MI controlled vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0640). Multiple parameters separated by "|".
  1. **Creation date** Representation as yyyy/mm/dd.
  1. **Update date** Representation as yyyy/mm/dd.
  1. **Checksum for interactor A**, for instance the ROGID of the interactor. Representation as databaseName:checksum
  1. **Checksum for interactor B**, for instance the ROGID of the interactor. Representation as databaseName:checksum
  1. **Checksum for interaction**, for instance the RIGID of the interaction. Representation as databaseName:checksum
  1. **negative** Boolean value to distinguish positive interactions (negative = false) from negative interactions (negative = true)

All the columns are mandatory.

## Syntax ##

Columns are normally formed by fields delimited by "|", with a structure like this one:

```
<XREF>:<VALUE>(<DESCRIPTION>)
```

Due to the unsafe use of reserved characters in the values, we have recently added the possibility to surround `<XREF>`, `<VALUE>` or `<DESCRIPTION>` with quotes if they contain a special symbol.

In MI-TAB, the reserved characters are:

```
|
(
)
:
\t (tabulation)
```

Whenever this happen in your data, surround the value with double quotes:

```
"<XREF_WITH_RESERVED_CHARS>":"<VALUE_WITH_RESERVED_CHARS>"("<DESCRIPTION>")
```

Note that the quotes are before and after each part. The escaped data should look like in the following examples:

```
psi-mi:"MI:0000"(a cv term)
psi-mi:"MI:0000"("I can now use braces ()()() or pipes ||| here and ::colons::")
```
If you want to use a quote within a quote, escape it:

```
uniprotkb:P12345("a \"nice\" protein")
```
