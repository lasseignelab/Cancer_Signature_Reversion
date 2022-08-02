
# Parallel gene set signature reversion reveals drug repurposing candidates for human cancers

Here we compare and contrast three methods for identifying disease signatures for downstream signature reversion drug repurposing candidate identification and demonstrate their ability to yield many novel drug repurposing candidates for the cancers with the lowest relative survival rates. Because our methodology relies on patient tumor RNA-Seq profiles from The Cancer Genome Atlas (TCGA) [1–4], LINCS 2020 data [5], and cancer-specific cell line omic profiles from DepMAP[6] and PRISM[6] we focused on low survival cancers where this data was available, namely pancreatic adenocarcinoma (5-year survival of less than 8% [7] liver hepatocellular carcinoma (5-year survival of 18%)[8], glioblastoma (5-year survival rate of 4%) [9], and lung adenocarcinoma (5-year survival of 5% for metastatic cases) [10]. By evaluating the different methods across these cancers, we found that the various methods detected distinct disease signatures to determine candidates, resulting in mostly unique drug candidates. We conclude that one disease signature method did not outperform the others. Future studies should consider using all these methods to determine drug repurposing candidates or develop a strategy to combine these disease signatures.


## Authors

- [Jennifer L. Fisher](https://www.github.com/JenFisher7), [Elizabeth J. Wilk](), [Victoria L Flanary](), [Vishal H. Oza](), [Brittany N. Lasseigne]()

Department of Cell, Developmental and Integrative Biology, Heersink School of Medicine, University of Alabama at Birmingham, Birmingham, AL, 35294, USA.

## Dockers
In addition to the scripts here, the main Docker image used for this analysis is publicly available on Docker Hub (jenfisher7/rstudio_tf_dr_v3). For the drug structure similarity analysis, a different Docker image was used (jenfisher7/rstudio_sex_bias_analysis).

## Scripts

- 211213_recount3_download.Rmd
- 220728_plier_recount3_wo_gtex_tcga.Rmd
- 220112_gbm_deseq2_transfer_learning.Rmd
- Tau value calculations for GI1
- 220118_GBM_SignatureSearch.Rmd
- 220405_limma_GBM.Rmd 
- 220523_pca_analysis_other_cancers.Rmd
- Tau value calculations for other cancer cell lines
- 220601_Liver_SignatureSearch.Rmd
- 220606_lung_cancer_signaturesearch.Rmd
- 220607_PAAD_SignatureSearch.Rmd
- 220608_gbm_CT_PRSIM_UPDATE.Rmd
- 220614_LINCS_profile_candidates_all_cancers.Rmd
- 220627_more_methods_comparsions.Rmd
- 220323_PLIER_LVs.Rmd
- 220315_figure2_additional.Rmd <- this needs heavy adjustment
- Drug structure similarity analysis 
- 220503_PRISM_top_candidates_plotting.Rmd

## Lasseigne Lab 
<img src="https://www.lasseigne.org/img/main/lablogo.png" width="200" height="200">



## Acknowledgements

 - Lasseigne Lab Members

## Funding

- RO3, etc. 

## References

1. Cancer Genome Atlas Research Network. Electronic address: andrew_aguirre@dfci.harvard.edu, Cancer Genome Atlas Research Network. Integrated Genomic Characterization of Pancreatic Ductal Adenocarcinoma. Cancer Cell. 2017;32:185–203.e13.
2. Cancer Genome Atlas Research Network. Electronic address: wheeler@bcm.edu, Cancer Genome Atlas Research Network. Comprehensive and Integrative Genomic Characterization of Hepatocellular Carcinoma. Cell. 2017;169:1327–41.e23.
3. Cancer Genome Atlas Research Network. Comprehensive molecular profiling of lung adenocarcinoma. Nature. 2014;511:543–50.
4. Brennan CW, Verhaak RGW, McKenna A, Campos B, Noushmehr H, Salama SR, et al. The somatic genomic landscape of glioblastoma. Cell. 2013;155:462–77.
5. Yang C, Zhang H, Chen M, Wang S, Qian R, Zhang L, et al. A survey of optimal strategy for signature-based drug repositioning and an application to liver cancer. Elife [Internet]. 2022;11. Available from: http://dx.doi.org/10.7554/eLife.71880
6. DepMap: The Cancer Dependency Map Project at Broad Institute [Internet]. [cited 2022 May 25]. Available from: https://depmap.org/portal/depmap/
7. Orth M, Metzger P, Gerum S, Mayerle J, Schneider G, Belka C, et al. Pancreatic ductal adenocarcinoma: biological hallmarks, current status, and future perspectives of combined modality treatment approaches. Radiat Oncol. 2019;14:141.
8. Villanueva A. Hepatocellular Carcinoma. N Engl J Med. 2019;380:1450–62.
9. Poon MTC, Sudlow CLM, Figueroa JD, Brennan PM. Longer-term (≥ 2 years) survival in patients with glioblastoma in population-based studies pre- and post-2005: a systematic review and meta-analysis. Sci Rep. 2020;10:11622.
10. Huang C-Y, Chen B-H, Chou W-C, Yang C-T, Chang JW-C. Factors associated with the prognosis and long-term survival of patients with metastatic lung adenocarcinoma: a retrospective analysis. J Thorac Dis. 2018;10:2070–8.



## License

TBD

