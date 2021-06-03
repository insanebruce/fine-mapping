# Fine-mapping

## CSE 284 Final Project, Spring 2021

**Title**: Applying fine-mapping techniques to summary statistics from a GWAS of Alzheimer’s disease in European Population

**Authors**: Jianing Wang(**@insanebruce**), Hanqing Zhao (**@HanqingZhao97**)

## Folder Structure

```txt
.
├── bin
|   ├── 00_set_up.sh      # install fine-mapping softwares
|   └── ...
├── images                # all images/plots
|   ├── max_causal_1
|   |   ├── venn_1.png
|   |   ├── chr1-rs679515.png
|   |   ├── chr1-rs679515_credset1.png
|   |   └── ...
|   ├── max_causal_2
|   |   ├── venn_2.png
|   |   ├── block1_finemap.png
|   |   ├── block1_caviarbf.png
|   |   ├── block1_paintor.png
|   |   └── ...
|   ├── manhattan.png
|   └── ...
├── images                 # input files
|   └── README
├── output                 # output files 
|   ├── def_param_tot_cred_set.txt
|   ├── def_param_nohup.out
|   └── ...
├── ref                    # reference panel
|   ├── 01_prepare_reference.py
|   └── blocks.txt
├── analysis.ipynb         # our main code
├── fine_map_pipe.py       # the fine-mapping pipeline
├── slides.pdf             # the presentation slides
├── report.pdf             # the final report
└── README.md
```

## Sumpplmentary Data

`output/summary_significant_blocks.txt`: identified 13 causal blocks.

### Max causal variant allowed = 1 (default)

* `output/def_param_nohup.out`: *nohup* outputs, including execution time for each software.
* `output/def_param_tot_cred_set.txt`: the output credible sets.
* `output/proc_res.txt`: the credible sets with dbSNP annotations.
* `images/max_causal_1`: regional plots for each causal block. The top variant is selected to generate the plots using LocusZoom.

### Max causal variant allowed = 2

* `output/nohup.out`: *nohup* outputs, including execution time for each software.
* `output/summary_total_credible_set.txt`: the output credible sets.
* `output/proc_res2.txt`: the credible sets with dbSNP annotations.
* `images/max_causal_2`: regional plots for each causal block. The top variant from each credible set is selected for plotting using LocusZoom.

## References

GWAS summary statistics used here can be downloaded from this [link](http://ftp.ebi.ac.uk/pub/databases/gwas/summary_statistics/GCST002001-GCST003000/GCST002245/).

`bin\00_set_up.sh`, `ref\01_prepare_reference.py`, and `fine_map_pipe.py` are adapted from this [repository](https://github.com/mulinlab/CAUSALdb-finemapping-pip).

*PAINTOR*: [source](https://github.com/gkichaev/PAINTOR_V3.0)

*CAVIARBF*: [source](https://bitbucket.org/Wenan/caviarbf/src/master/)

*FINEMAP*: [source](http://www.christianbenner.com)

See *References* section of the report for the complete list of references.

## Notes

* All scripts and softwares were run on UCSD DataHub.
* We used 1000 Genomes Phase 1 data to build the LD reference panel. The input data and output genotype matrices and vcf files are not maintained in this repo due to the sizes.
* Actual input GWAS summary statistics is also not included in this repo due to the size.
