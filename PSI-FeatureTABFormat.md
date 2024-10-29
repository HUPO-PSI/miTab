# PSI-MI Feature TAB Format #

## Introduction ##

PSI-MI FeatureTab is a new format, it takes inspiration from the existing PSI-MI XML and tab-delimited formats (1, 2, 3), which is actively supported by the MI worktrack. Most users will continue to use PSI-MI MITAB or PSI-MI XML2.5/3.0 to exchange experimental-based interaction data, the PSI-MI FeatureTab will be required only for specialist use cases.

(1) https://pmc.ncbi.nlm.nih.gov/articles/PMC5896046/

(2) https://europepmc.org/article/MED/30602777

(3) https://europepmc.org/article/MED/30793173


## Column definitions ##

The column contents should be as follows:

  1. **Feature AC**, is designed to report the accession number for a feature such as mutations, binding sites, PTMs, etc. (ex. EBI-489661; EBI-1000504; EBI-1234567).
  1. **Feature short label**, contains human-readable short label summarizing the amino acid changes and their positions, compliant with the Human Genome Variation Society recommendations (see http://varnomen.hgvs.org/recommendations/protein/), in case of mutation features or the binding range involved in an interactions, the exact aa range.
  1. **Feature range(s)**, contains position(s) in the protein sequence involved in that specific feature (Ex: mutation, binding sites, PTMs, etc).
  1. **Original sequence**, contains the wild type amino acid residue(s) affected, in one letter code.
  1. **Resulting sequence**, contains the replacement sequence (or deletion) in one letter code.
  1. **Feature type**, contains the feature type, following the PSI-MI controlled vocabularies (EX: mutation (MI:0118); mutation decreasing (MI:0119); mutation disrupting strength(MI:1128); Necessary binding region (MI:0429), etc.)
  1. **Feature annotation**, contains specific comments, on free text, about the annotated feature that can be of interest.
  1. **Affected protein AC**, contains affected protein identifier (preferably UniProtKB accession, if available, Ex: uniprotkb:P12346). It is represented as databaseName:identifier, where databaseName is the name of the corresponding database as defined in the [PSI-MI controlled vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0444), and identifier is the unique primary identifier of the molecule in the database.
  1. **Affected protein symbol**, contains the protein symbol  of the protein affected by a specific feature, as given by UniProtKB (EX. Gene name, DLG4).
  1. **Affected protein full name**, contains the protein full name of the protein affected by a specific feature, as given by UniProtKB (EX. DLG4, Postsynaptic density protein 95 Synapse-associated protein 90 ).
  1. **Affected protein organism**, contains the TaxID and species name as given by UniProtKB. It is represented as taxid:identifier(organism name) where the identifier is the taxon id of the organism and organism name can either be the common name or scientific name (EX. 9606 - Homo sapiens).
  1. **Interaction participants**, contains information about the identifiers for all participants in the affected interaction, along with their species and molecule type between brackets. Ex.: (uniprotkb:P15153(protein(MI:0326), 9606 - Homo sapiens)|ensembl:ENSP00000356505.4(protein(MI:0326), 9606 - Homo sapiens)).
  1. **PubMedID**, contains the reference to the publication where the interaction evidence was reported. It is recommended to give one pubmed id per MITAB line and IMEx ids can be added. Ex: pubmed:16980971|imex:IM-1
  1. **Figure legend**, contains the reference to the specific figures in the paper where the interaction evidence was reported.
  1. **Interaction AC**, describes the interaction accession within our databases. This can be used to obtain further information about the interaction (EX.: EBI-489644; EBI-8285478).
  1. **Xref ID**, contains whenever is available the Xref Identifier associated to a feature.It is represented as databaseName:ac(text), where databaseName is the name of the corresponding database as defined in the [PSI-MI controlled vocabulary](https://www.ebi.ac.uk/ols4/ontologies/mi/classes/http%253A%252F%252Fpurl.obolibrary.org%252Fobo%252FMI_0444), and ac is the primary accession in the database. For example, the InterPro cross references associated to a binding domain. Multiple cross references separated by "|".

Empty columns should be represented with '-' to keep track of the columns.

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
