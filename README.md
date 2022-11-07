
# Divergent disease signatures for signature reversion drug repurposing reveal promising candidates for low-survival human cancers

Background:

New therapies are critical to increased cancer survival, the leading cause of death worldwide. Drug repurposing is a promising approach as re-approving a drug requires less time and cost than drug discovery methods. A previously successful computionational method, signature reversion, leverages disease signatures and cell line perturbation signatures to detect perturbation signatures that are inversely related to disease signatures. However, there are limited signature reversion studies that assess the performance and biological relevance of disease signatures derived from different methods.  

Results: 

While identifying new repurposing candidates for four low-survival cancers (i.e., pancreatic adenocarcinoma, liver hepatocellular carcinoma, glioblastoma, and lung adenocarcinoma), we evaluated three methods for developing a disease signature: two differential gene expression methods limma and DESeq2 and MultiPLIER, a transfer learning approach. We used drugs in previous clinical trials and drug response in cancer cell lines as controls. Across the cancers, all the methods were significant at least once in both controls, and for each cancer, we found two or more methods were significant across the controls. However, within each of the cancers, the maximum overlap was one candidate. Thus, we hypothesize that the methods identify unique, efficacious candidates because they perturb divergent disease signatures. To investigate these disease signatures, we conducted several analyses including drug-drug perturbation similarity networks where we found that different methods are not preturbing the same disease pathways.  

Conclusion: 

By considering all these methods that construct divergent disease signatures, we discovered more promising candidates for low-survival cancers than by one method alone. 

## Authors

- [Jennifer L. Fisher](https://www.github.com/JenFisher7), [Elizabeth J. Wilk](https://github.com/lizzyjoan), [Victoria L Flanary](https://github.com/vlflanary121), [Vishal H. Oza](https://github.com/vishaloza), [Brittany N. Lasseigne](https://github.com/blasseigne)

Department of Cell, Developmental and Integrative Biology, Heersink School of Medicine, University of Alabama at Birmingham, Birmingham, AL, 35294, USA.

## Dockers and Conda Environment
In addition to the scripts here, the Docker images used for this analysis is publicly available on Docker Hub (jenfisher7/rstudio_cancer_dr & jenfisher7/rstudio_tf_dr_v3). For the tau calculations, a conda environment was used (SR_TAU_CELL_environment.yml).

## Scripts

**Download data**

Data was downloaded to the UAB Cheaha Cluster. The Docker/singularity (jenfisher7/rstudio_tf_dr_v3) was used for this download and for the PLIER transfer learning step. 
Docker: jenfisher7/rstudio_tf_dr_v3

- 211213_recount3_download.Rmd
- Download scripts: data/recount3/gbm_gene_url_8.sh (1-8)

**PLIER for transfer Learning**
- 220728_plier_recount3_wo_gtex_tcga.Rmd

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

For Lung Cancer
 - 220526_tau_calc_A549.R
 - 220526_tau_calc_A549.sh

Combine list for lung, liver, and pancreatic cancer from array runs
 - 220601_tau_A549_HEPG2_YAPC_df.R
 - 220601_tau_A549_HEPG2_YAPC_df.sh

**Disease signature development and signature reversion for glioblastoma, lung, liver, and pancreatic cancer**

Docker: jenfisher7/rstudio_cancer_dr

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
- 220805_network_differences_methods.Rmd
- 220706_drug_structure_test_gbm.Rmd 
- 220920_disease_genes_plots.Rmd

**Additional transfer learning analysis**
- 220427_transfer_learning_gene_label_testing.Rmd
- 220323_PLIER_LVs.Rmd

**GBM candidate selection and candidate testing analysis**

Docker: jenfisher7/rstudio_cancer_dr

- 220503_PRISM_top_candidates_plotting.Rmd

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

 - Lasseigne Lab Members

## Funding

- RO3, etc. 

## License

MIT 

Details in LICENSE file.

