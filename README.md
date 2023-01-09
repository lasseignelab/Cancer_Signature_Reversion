
# Signature reversion of three disease-associated signature approaches prioritizes drug repurposing candidates for low-survival human cancers

Background:

New therapeutic options are critical to increased cancer patient survival. Drug repurposing is promising, as approving a drug for a new indication requires less time and cost than for a new drug. Signature reversion leverages disease-associated and cell line drug perturbation gene signatures to detect which drug perturbation signatures are most inversely related to the disease signatures so that the drug may reverse the disease signature. Here we sought to assess the performance and biological relevance of different disease-associated gene signature approaches and identify novel drug repurposing candidates for pancreatic adenocarcinoma, liver hepatocellular carcinoma, glioblastoma, and lung adenocarcinoma, four low-survival cancers.  

Results: 

 For the differential gene expression methods limma and DESeq2 and the transfer learning method MultiPLIER, we evaluated the identified disease-associated gene expression signatures and their signature reversion drug repurposing candidates. Across the four cancers, almost all of the disease-associated signature reversion repurposing results were enriched for unique candidates either in previous clinical trials or that performed well in the PRISM drug screen. Additionally, we further tested the GBM candidates pamidronate and nimodipine and found that they inhibit GBM cell growth in the U251 cell line and the JX39 PDX in vitro models.

Conclusion: 

We conclude that one disease-associated gene signature approach did not outperform the others so future studies should consider using multiple signatures to determine drug repurposing candidates for further screening. We also identify prioritized drug repurposing candidates for four of the most deadly human cancers, providing a resource for future research studies. 


## Authors

- [Jennifer L. Fisher](https://www.github.com/JenFisher7), [Elizabeth J. Wilk](https://github.com/lizzyjoan), [Vishal H. Oza](https://github.com/vishaloza), [Timothy C. Howton](https://github.com/tchowton), [Victoria L Flanary](https://github.com/vlflanary121), [Amanda D. Clark](https://github.com/adc0032), Anita B. Hjelmeland , & [Brittany N. Lasseigne](https://github.com/blasseigne)

Department of Cell, Developmental and Integrative Biology, Heersink School of Medicine, University of Alabama at Birmingham, Birmingham, AL, 35294, USA.

## Dockers and Conda Environment
In addition to the scripts here, the Docker images used for this analysis is publicly available on Docker Hub ([jenfisher7/rstudio_cancer_dr](https://hub.docker.com/r/jenfisher7/rstudio_cancer_dr) & [jenfisher7/rstudio_tf_dr_v3](https://hub.docker.com/r/jenfisher7/rstudio_tf_dr_v3)). For the tau calculations, a conda environment was used (SR_TAU_CELL_environment.yml).

## Scripts

**Download data**

Data was downloaded to the UAB Cheaha Cluster. The Docker/singularity (jenfisher7/rstudio_tf_dr_v3) was used for this download and for the PLIER transfer learning step. 
Docker: jenfisher7/rstudio_tf_dr_v3

- 211213_recount3_download.Rmd
- Download scripts: data/recount3/gbm_gene_url_8.sh (1-8)

Note that in Dec. 2022, Recount3's server changed resulting in the current version of Recount3 in the dockers to not function correctly. However, we do provide the urls from Recount3 to download the data for the 211213_recount3_download.Rmd and data/recount3/gbm_gene_url_8.sh (1-8) scripts. In addition, scripts in the following sections have been adjusted to use the url downloaded data from Recount3: **Disease signature development and signature reversion for glioblastoma, lung, liver, and pancreatic cancer**, **Compare candidates and disease signatures**, & **GBM candidate selection and candidate testing analysis**. 

**PLIER for transfer Learning**
- 220728_plier_recount3_wo_gtex_tcga.Rmd

**Package versions for the Docker/singulairty**
- 221221_rstudio_tf_dr_v3_singularity.Rmd

**Tau value calcuation for signature reversion**

These scripts use the conda environment file SR_TAU_CELL_environment.yml. The ".sh" file was used to submit the cluster job on a slurm system in an array format. The R scripts were executed by these cluster job scripts. This allowed for more parrallel runs of the tau calculations. 

Set Up for Tau Calculations:
 - 220125_conda_set_up.txt
 - 220125_TAU_values_LINCS.R
 - 220125_TAU_values_LINCS_test.sh

For GBM:
 - 220125_TAU_calc_LINCS_step2_v3.R
 - 220125_TAU_calc_LINCS_step2_v4.sh
 - 220203_tau_calc_1HAE.R 
   - needed for the 220208_tau_GBM_1HAE.sh script but the 1HAE cell line tau values are not used in any other script of the project
 - 220203_tau_calc_1HAE.sh 
   - needed for the 220208_tau_GBM_1HAE.sh script but the 1HAE cell line tau values are not used in any other script of the project
 - 220208_tau_GBM_1HAE.sh
 
For Pancreatic Cancer:
 - 220526_tau_calc_YAPC.R
 - 220526_tau_calc_YAPC.sh

For Liver Cancer: 
 - 220526_tau_calc_HEPG2.sh
 - 220526_tau_calc_HEPG2.R

For Lung Cancer:
 - 220526_tau_calc_A549.R
 - 220526_tau_calc_A549.sh

Combine list for lung, liver, and pancreatic cancer from array runs:
 - 220601_tau_A549_HEPG2_YAPC_df.R
 - 220601_tau_A549_HEPG2_YAPC_df.sh
 
 Package version for the conda environment:
 - 221221_conda_packages.R
 - 221221_conda_packages.sh
 
**Download recount3 for downstream analysis**
- 221219_recount3_download_fix.sh

**Disease signature development and signature reversion for glioblastoma, lung, liver, and pancreatic cancer**

Docker: jenfisher7/rstudio_cancer_dr
- 221219_recount3_fix.Rmd
- 220808_PRISM_data.Rmd
- 220112_gbm_deseq2_transfer_learning.Rmd
- 220118_GBM_SignatureSearch.Rmd
- 220405_limma_GBM.Rmd 
- 220523_pca_analysis_other_cancers.Rmd
- 220601_Liver_SignatureSearch.Rmd
- 220606_lung_cancer_signaturesearch.Rmd
- 220607_PAAD_SignatureSearch.Rmd

**Compare candidates and disease signatures**

Docker: jenfisher7/rstudio_cancer_dr

- 220608_gbm_CT_PRSIM_UPDATE.Rmd
- 220614_LINCS_profile_candidates_all_cancers.Rmd
- 220627_more_methods_comparsions.Rmd
- 220323_PLIER_LVs.Rmd
- 220805_network_differences_methods.Rmd
- 220706_drug_structure_test_gbm.Rmd 
- 220920_disease_genes_plots.Rmd
- 220427_transfer_learning_gene_label_testing.Rmd

**GBM candidate selection and candidate testing analysis**

Docker: jenfisher7/rstudio_cancer_dr

- 220503_PRISM_top_candidates_plotting.Rmd
- 221130_gbm_drug_testing_res.Rmd

**Package versions for the Docker rstudio_cancer_dr**
- 221221_rstudio_cancer_dr_info.Rmd

**Function scripts**
- functions_cancer_signature_reversion_JLF.R
  - This a script with functions for the analysis scripts above. Most of the functions were written by Jennifer Fisher. However, some of the functions were developed by others. These functions have a comment with them about who wrote the function and if there were any changes to them for our specific study. 
- signaturesearch_functions.R
  - This a script with functions from the singatureSearch R package for tau calculations. 
- plier_util.R
   - This is a script from the MultiPLIER paper. It contains functions used for the transfer learning components for this project. 
- test_LV_differences.R
  - This is a script from the MultiPLIER paper. It contains functions used for the transfer learning components for this project. 

## Lasseigne Lab 
<img src="https://www.lasseigne.org/img/main/lablogo.png" width="200" height="200">

## Acknowledgements

 - We would like to thank the all the Lasseigne Lab for providing feedback during this project.

## Funding

- JLF, VHO, ABH, and BNL are supported by R03OD030604 (to BNL); JLF and BNL are supported by an ACS-IRG (to BNL); Victoria Flanary is supported by the MSTP program; JLF, EJW, VHO, and TCH are supported by R00HG009678 (to BNL); JLF, TCH, VHO, and BNL are supported by UAB funds to the Lasseigne Lab. 

## License

MIT 

Details in LICENSE file.

## Package versions and computing system information

[Docker/singularity: jenfisher7/rstudio_tf_dr_v3](https://github.com/lasseignelab/Cancer_Signature_Reversion/blob/main/script/221221_rstudio_tf_dr_v3_singularity.html)

[Conda: SR_TAU_CELL_environment.yml](https://github.com/lasseignelab/Cancer_Signature_Reversion/blob/main/script/18063914.c0152.conda.packages.out.txt)

[Docker: jenfisher7/rstudio_cancer_dr](https://github.com/lasseignelab/Cancer_Signature_Reversion/blob/main/script/221221_rstudio_cancer_dr_info.html)
