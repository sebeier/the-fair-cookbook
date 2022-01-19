---
dummy: dummy
---

# [here comes the Title of the recipe]

**identifier:** [RX.X_FIXME](RX.X_FIXME)

**version:** [<version_number_FIXME>](version_number_FIXME)

___

**_Difficulty level:_** moderate :triangular_flag_on_post: :triangular_flag_on_post: :white_circle:  :white_circle: :white_circle: _FIXME

**_Reading time:_** _FIXME minutes 

**_Intended Audience:_** 

> :heavy_check_mark: set_value_FIXME, e.g. Data Scientist

> :heavy_check_mark: set_value_FIXME, e.g. Data Scientist


**_Recipe Type_**: set_value_FIXME, e.g. Hands on

**_Executable code_**: set_value_FIXME, [Yes,No]


[TOC]
## Table of Contents
1. [Main FAIRification Objectives](#Main%20FAIRification%20Objectives)
2. [Graphical Overview of the FAIRification Recipe Objectives](#Graphical%20Overview%20of%20the%20FAIRification%20Recipe%20Objectives)
3. Requirements
4. [FAIRification Objectives, Inputs and Outputs](#FAIRification%20Objectives,%20Inputs%20and%20Outputs)
5. [Capability & Maturity Table](#Capability%20&%20Maturity%20Table)
6. [Table of Data Standards](#Table%20of%20Data%20Standards)
7. [Main Content goes here...](#Main%20Content)
    * [... writing executable code](#Executable%20Code%20in%20Notebook)
    * [... creating workflow figures](#How%20to%20create%20workflow%20figures)
8. [License](#License)

---

## Main Objectives

The main objective of the recipe is to provide a means of submitting and tracking genotyping data in public repositories, with a particular focus on plants. This includes:
1) Submission of sample data and metadata information to BioSamples.
2) Submission of sequencing data and metadata to ENA.
3) Retrieval of the correct genome assembly for the genotyping experiment
4) Conversion of the resulting analysis file (in VCF format) to be FAIR
5) Submission of the genotyping results to EVA.

___


## Graphical Overview of the FAIRification Recipe Objectives

Note: use this section to provide a decision tree for the overall process described in the recipe
For more information about the syntax used to generate the diagram, please refer to the [following documentation](https://mermaid-js.github.io/mermaid/#/flowchart)

<!--
[![](https://mermaid.ink/img/eyJjb2RlIjoiZ3JhcGggTFI7XG4gICAgQShEYXRhIEFjcXVpc2l0aW9uKTo6OmJveCAtLT5CKFJhdyBEYXRhKTo6OmJveFxuICAgIEIgLS0-IEN7RkFJUiBieSBEZXNpZ259XG4gICAgQzo6OmJveC0tPnxZZXN8IEQoU3RhbmRhcmQgQ29tcGxpYW50IERhdGEpOjo6Ym94XG4gICAgQzo6OmJveCAtLT58Tm98IEUoVmVuZG9yIGxvY2tlZCBEYXRhKTo6OmJveFxuICAgIGNsYXNzRGVmIGJveCBmb250LWZhbWlseTphdmVuaXIsZm9udC1zaXplOjE0cHgsZmlsbDojMmE5ZmM5LHN0cm9rZTojMjIyLGNvbG9yOiNmZmYsc3Ryb2tlLXdpZHRoOjFweFxuICAgIGxpbmtTdHlsZSAwLDEsMiwzIHN0cm9rZTojMmE5ZmM5LHN0cm9rZS13aWR0aDoxcHgsY29sb3I6IzJhOWZjOSxmb250LWZhbWlseTphdmVuaXI7IiwibWVybWFpZCI6eyJ0aGVtZSI6bnVsbH0sInVwZGF0ZUVkaXRvciI6ZmFsc2V9)](https://mermaid-js.github.io/mermaid-live-editor/#/edit/eyJjb2RlIjoiZ3JhcGggTFI7XG4gICAgQShEYXRhIEFjcXVpc2l0aW9uKTo6OmJveCAtLT5CKFJhdyBEYXRhKTo6OmJveFxuICAgIEIgLS0-IEN7RkFJUiBieSBEZXNpZ259XG4gICAgQzo6OmJveC0tPnxZZXN8IEQoU3RhbmRhcmQgQ29tcGxpYW50IERhdGEpOjo6Ym94XG4gICAgQzo6OmJveCAtLT58Tm98IEUoVmVuZG9yIGxvY2tlZCBEYXRhKTo6OmJveFxuICAgIGNsYXNzRGVmIGJveCBmb250LWZhbWlseTphdmVuaXIsZm9udC1zaXplOjE0cHgsZmlsbDojMmE5ZmM5LHN0cm9rZTojMjIyLGNvbG9yOiNmZmYsc3Ryb2tlLXdpZHRoOjFweFxuICAgIGxpbmtTdHlsZSAwLDEsMiwzIHN0cm9rZTojMmE5ZmM5LHN0cm9rZS13aWR0aDoxcHgsY29sb3I6IzJhOWZjOSxmb250LWZhbWlseTphdmVuaXI7IiwibWVybWFpZCI6eyJ0aGVtZSI6bnVsbH0sInVwZGF0ZUVkaXRvciI6ZmFsc2V9)
-->


<div class="mermaid">
graph LR;
    A(Data Acquisition):::box -->B(Raw Data):::box
    B --> C{FAIR by Design}
    C:::box-->|Yes| D(Standard Compliant Data):::box
    C:::box -->|No| E(Vendor locked Data):::box
    classDef box font-family:avenir,font-size:14px,fill:#2a9fc9,stroke:#222,color:#fff,stroke-width:1px
    linkStyle 0,1,2,3 stroke:#2a9fc9,stroke-width:1px,color:#2a9fc9,font-family:avenir;
</div>

___


## Requirements

* technical requirements:
   * bash knowledge
   * ...
* recipe dependency:
   * read Recipe 1 first!
* knowledge requirement:
   * be sure to know what OBO is, or read it here: ...link to knowledge...

---

## Capability & Maturity Table

| Capability  | Initial Maturity Level | Final Maturity Level  |
| :------------- | :------------- | :------------- |
| Interoperability | minimal | repeatable |

Help to fill this table out can be found ...(not yet)...

----

## FAIRification Objectives, Inputs and Outputs

| Actions.Objectives.Tasks  | Input | Output  |
| :------------- | :------------- | :------------- |
| [text annotation](http://edamontology.org/operation_3778)   | [MIAPPE](https://fairsharing.org/FAIRsharing.nd9ce9)  | [annotated text](http://edamontology.org/data_3779)  |
| [conversion](http://edamontology.org/operation_3434)  | [Variant File Format (.vcf)](https://fairsharing.org/FAIRsharing.cfzz0h) | [annotated text](http://edamontology.org/data_3779) |
| [format validation](http://edamontology.org/operation_0336) | [Variant File Format (.vcf)](https://fairsharing.org/FAIRsharing.cfzz0h)  | [report](http://edamontology.org/data_2048)  |
| [format validation](http://edamontology.org/operation_0336)  | [MIAPPE](https://fairsharing.org/FAIRsharing.nd9ce9) | [report](http://edamontology.org/data_2048)  |


## Table of Data Standards

| Data Formats  | Terminologies | Models  |
| :------------- | :------------- | :------------- |
| [FASTQ](https://fairsharing.org/FAIRsharing.r2ts5t) | [LOINC](https://fairsharing.org/FAIRsharing.2mk2zb)  | [SRA XML](https://fairsharing.org/FAIRsharing.q72e3w)  |
| [FASTA](https://fairsharing.org/FAIRsharing.rz4vfg) |  |  |
| [MIAPPE](https://fairsharing.org/FAIRsharing.nd9ce9) |  |  |
| [Variant File Format (.vcf)](https://fairsharing.org/FAIRsharing.cfzz0h) |  |  | 
| [BioSamples - Plant MIAPPE checklist](https://www.ebi.ac.uk/biosamples/schemas/certification/plant-miappe.json) |  |  |

## Table of Software and Tools

| Tool Name |
| :------------- |
| [github](https://github.com/)  |
| [BioSamples](https://www.ebi.ac.uk/biosamples/) |
| [European Nucleotide Archive](https://www.ebi.ac.uk/ena/browser/home) |
| [European Variation Archive](https://www.ebi.ac.uk/eva/) |
| [VCF Validator](https://github.com/EBIvariation/vcf-validator/wiki/User's-Guide) |
___

## Main Content

In order to ensure interoperability of VCF files, the following VCF meta-information lines should be used:
* Obligatory meta-information line :  
  * **`##fileformat`** : Version of the VCF file format used.  
  
    Examples:
    
    File is in Version 4.3 of the VCF file format.
    ```
    ##fileformat=VCFv4.3  
    ```
    File is in Version 4.1 of the VCF file format.
    ```
    ##fileformat=VCFv4.1
    ```
* Recommended meta-information lines :  
  * **`##bioinformatics_source (URL or URI)`**: Analytic approach usually consisting of chains of bioinformatics tools for creating the VCF file specified as the DOI of a publication, or more generally as URL/URI, like a public repository for the scripts used. 
  *  
    Examples:
    
    Description of a GBS experiment in barley and subsequent read alignment and variant calling using a bioinformatics analysis pipeline consisting of cutadapt, BWA-MEM, SAMtools, NovoSort, Picard, BCFtools and seqArray.
    ```
    ##bioinformatics_source=”doi.org/10.1038/s41588-018-0266-x” 
    ```
    Description of a GBS experiment in maize and subsequent read alignment and variant calling using a bioinformatics analysis pipeline consisting of cutadapt, CD-HIT-EST, Bowtie2, freebayes, TASSEL 5, VCFtools, BWA-MEM.
    ```
    ##bioinformatics_source=”doi.org/10.3389/fpls.2021.628439”
    ```
  * **`##reference_ac (assembly_accession)`**: Accession number, including the version, of the reference sequence on which the variation data of the present VCF is based.  
    
    Examples:
    
    Reference genome assembly for barley (*Hordeum vulgare*) cultivar Morex version 2.
    ```
    ##reference_ac=GCA_902498975.1  
    ```
    Reference genome assembly for maize (*Zea mays*) cultivar B73 version 3.
    ```
    ##reference_ac=GCA_000005005.5 
    ```
  * **`##reference_url (DOI)`**: A DOI (or URL/URI) for downloading of this reference genome, preferably from one INSDC archive.  
    
    Examples: 
    
    Reference genome assembly for barley (*Hordeum vulgare*) cultivar Morex version 2 download link on NCBI FTP.
    ```
    ##reference_url=”ftp.ncbi.nlm.nih.gov/genomes/all/GCA/902/498/975/GCA_902498975.1_Morex_v2.0/GCA_902498975.1_Morex_v2.0_genomic.fna.gz”  
    ```
    Reference genome assembly for maize (*Zea mays*) cultivar B73 version 3 download link on NCBI FTP.
    ```
    ##reference_url=”ftp.ncbi.nlm.nih.gov/genomes/all/GCA/000/005/005/GCA_000005005.5_B73_RefGen_v3/GCA_000005005.5_B73_RefGen_v3_genomic.fna.gz”
    ```
  * **`##contig (<ID=ctg1, length=sequence_length, assembly=gca_accession, md5=md5_hash, species=NCBI Taxon ID>)`** : The individual sequence(s) of the reference genome  
    
    Examples:
    
    Chromosome 1H of barley (*Hordeum vulgare*) cultivar Morex version 2.
    ```
    ##contig=<ID=chr1H,length=522466905,assembly=GCA_902498975.1,md5=8d21a35cc68340ecf40e2a8dec9428fa,species=NCBITaxon:4513>  
    ```
    Chromosome 1 of maize (*Zea mays*) cultivar B73 version 3.
    ```
    ##contig=<ID=GK000031.3,length=301433382,assembly=GCA_000005005.5,md5=74dfe85ad898416814fa98e8d7048f76,species=NCBITaxon:4577>
    ```
  * **`##SAMPLE(<ID=BioSample_accession, DOI=doi, ext_ID=registry:identifier>)`** : Describe the material whose variants are given in the genotype call columns in greater detail and can be extended using the specifications of the VCF format. In case no DOI is registered with the material the field ext_ID holds an external identifier (resolvable through identifiers.org (Wimalaratne et al., 2018) in the notation ‘registry:identifier’). If the database is not registered with identifiers.org, the DNS of the holding institution and the identifier scheme should be provided (see example below). For multiple external IDs the field should be used multiple times (delimited by commas).
   
    Examples:
    
    One genotype from the barley (*Hordeum vulgare*) GBS experiment.
    ```
    ##SAMPLE=<ID=SAMEA7836897,DOI="doi.org/10.25642/IPK/GBIS/17527",ext_ID="GBIS.IPK-GATERSLEBEN.DE/akzessionId:7811152">  
    ```
    One genotype from the maize (*Zea mays*) GBS experiment.
    ```
    ##SAMPLE=<ID=SAMEA9111398>
    ```
* Optional meta-information lines :  
  * **`##fileDate`**: Creation date of the VCF in the basic form without separator: YYYYMMDD  
    
    Examples:
    
    File was created on October 28, 2021.
    ```
    ##fileDate=20211028  
    ```
    File was created on March 16, 2012.
    ```
    ##fileDate=20120316
    ```
  * In case of adding new fields : Please check the official format specifications to avoid redundancy and possible incompatibilities.

### ... write executable code


```python
import isatools
import json
import pandas as pd 
import holoview
```


### ... create workflow figures

one may use the following **[mermaid](https://mermaid-js.github.io/mermaid/#/)** syntax:

```
graph LR;
    A[Data Acquisition] -->B(Raw Data)
    B --> C{FAIR by Design}
    C -->|Yes| D[Standard Compliant Data]
    C -->|No| E[Vendor locked Data]
```

<div class="mermaid">
graph LR;
    A["input data"]-->B["conversion to open format"];
    A["input data"]-->C["automatic annotation"];
    B["conversion to open format"]-->D(("output data"));
    C["automatic annotation"]-->D(("output data"));  

    style A fill:#FF5733,stroke:#333,stroke-width:2px
    style D fill:#0A749B,stroke:#333,stroke-width:2px
</div>

___

## Conclusion:

> Summerize Key Learnings of the recipe.
> 
> Suggest further reading using the following:
> #### What should I read next?
> * [HackMD & MarkDown Tips and Tricks](TODO)
> * [A related recipe which nice complements the current one ](TODO)

___

## Reference

* [RDMkit - Tools Assembly - Plant Genomics](https://rdmkit.elixir-europe.org/plant_genomics_assembly.html)
* [Training Material from FONDUE Datathon 2021](https://github.com/PBR/elixir-fondue-datathon)
___

## Authors:

| Name | Affiliation  | orcid | CrediT role  | specific contribution |
| :------------- | :------------- | :------------- |:------------- |:------------- |
| Sebastian Beier |  Forschungszentrum Jülich, IPK Gatersleben, ELIXIR-DE| [0000-0002-2177-8781](https://orcid.org/0000-0002-2177-8781) | Writing - Original Draft | original format |
| Uwe Scholz |  IPK Gatersleben, ELIXIR-DE | [0000-0001-6113-3518](https://orcid.org/0000-0001-6113-3518)| Writing - Review & Editing, Funding acquisition | | 

___



## License:

This page is released under the Creative Commons 4.0 BY license.

<a href="https://creativecommons.org/licenses/by/4.0/"><img src="https://mirrors.creativecommons.org/presskit/buttons/80x15/png/by.png" height="20"/></a>

test
