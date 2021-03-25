<img align="right" width="200" src="img/logo.png">

Helix PGx Database
===============================
Frequency tables for pharmacogenomics alleles and genotypes as called by the Helix® PGx pipeline.

This data is being made available via the [Creative Commons Attribution Non-Commercial Share Alike license](https://creativecommons.org/licenses/by-nc-sa/4.0/deed.en)

<p align="right">
<a href="https://creativecommons.org/licenses/by-nc-sa/4.0/deed.en"><img src="https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg"></a>
</p>

## 📚 Datasets

### Star allele frequency table [star_allele_frequencies.tsv]
| Column | Description |
|-------------|-------------|
| gene | The HGNC gene symbol. |
| allele | Star allele designation. |
| PV id | PharmVar identifier.  Can be resolved by appending the numeric id to the end of the URL: https://www.pharmvar.org/haplotype/ |
| function | Annotated allele function sourced from [PharmVar API](https://www.pharmvar.org/documentation). |
| SV | Whether this allele is a structural variant, e.g. a hybrid allele or whole gene deletion/duplication. |
| overall freq | Population frequency of the star allele in this study. |
| non EUR freq | Frequency of star allele within the set of individuals who were not predominant EUR ancestry.  Non EUR determined by <=80% EUR Admixture value. |
| AFR freq | Frequency of star allele within the set of individuals assigned to the Africa (AFR) population in this study.  AFR determined by >80% Admixture value. |
| AMR freq | Frequency of star allele within the set of individuals assigned to the Americas (AMR) population in this study.  AMR determined by >80% Admixture value. |
| EAS freq | Frequency of star allele within the set of individuals assigned to the East Asia (EAS) population in this study.  EAS determined by >80% Admixture value. |
| EUR freq | Frequency of star allele within the set of individuals assigned to the Europe (EUR) population in this study.  EUR determined by >80% Admixture value. |
| SAS freq | Frequency of star allele within the set of individuals assigned to the South Asia (SAS) population in this study.  SAS determined by >80% Admixture value. |
| OTHER freq | Frequency of star allele within the set of individuals that could not be readily assigned a specific population in this study. |



### Genotype-to-phenotype frequency table [genotype_phenotype_frequencies.tsv]
| Column | Description |
|-------------|-------------|
| gene | The HGNC gene symbol. |
| alleles | Comma delimited list of all star alleles comprising the genotype. Novel pLoF alleles are listed at the end with the format chr#:POS, where POS is the position in hg38. "Incomplete Match" is appended when the reported allele combination does not completely explain the variants supported by the underlying data.|
| alleles amp | Reformatted list of alleles, using the amplification syntax.  For example, `(*1, *1, *1)` would be rewritten as `(*1, *1x2)`. |
| activity scores | Comma delimited list of activity scores for each allele in column 2. Novel pLoF variants and incomplete matches default to "null".|
| metabolizer status | Metabolic status for the gene derived from the activity score. Defaults to "Unknown" if genotype contains an incomplete match or includes an allele of Unknown fuction.|
| risk | CPIC assignment of PGx risk dependent on metabolizer status using EHR Priority Result Notation. Defaults to "Unknown" if genotype is an incomplete match. (A _priority result_ is defined as a genetic test result that results in a change in drug, drug dose, or drug monitoring.)|
| overall gt freq | Population frequency of the genotype in this study. |
| non EUR gt freq | Frequency of genotype within the set of individuals who were not predominant EUR ancestry.  Non EUR determined by <=80% EUR Admixture value. |
| AFR gt freq | Frequency of genotype within the set of individuals assigned to the Africa (AFR) population in this study.  AFR determined by >80% Admixture value. |
| AMR gt freq | Frequency of genotype within the set of individuals assigned to the Americas (AMR) population in this study.  AMR determined by >80% Admixture value. |
| EAS gt freq | Frequency of genotype within the set of individuals assigned to the East Asia (EAS) population in this study.  EAS determined by >80% Admixture value. |
| EUR gt freq | Frequency of genotype within the set of individuals assigned to the Europe (EUR) population in this study.  EUR determined by >80% Admixture value. |
| SAS gt freq | Frequency of genotype within the set of individuals assigned to the South Asia (SAS) population in this study.  SAS determined by >80% Admixture value. |
| OTHER gt freq | Frequency of genotype within the set of individuals that could not be readily assigned a specific population in this study. |

