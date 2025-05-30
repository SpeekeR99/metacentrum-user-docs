# AlphaFold
[AlphaFold](https://www.deepmind.com/research/highlighted-research/alphafold) is a cutting-edge software tool designed to predict the three-dimensional (3D) structures of proteins. Developed by DeepMind, AlphaFold has revolutionized the field of structural biology by providing accurate predictions of 3D models of protein structures, which is crucial for understanding their functions and interactions.


## Running Alphafold in OnDemand

For users who want to run AlphaFold without requiring extensive computational resources or expertise, the OnDemand service provides a convenient and user-friendly solution. This web-based interface allows users to submit AlphaFold jobs directly from their browser, leveraging the MetaCentrum infrastructure.

To use AlphaFold OnDemand, follow these steps:

* Access the [OnDemand portal](https://ondemand.metacentrum.cz) and navigate to the `Job Composer`.
* Select the `Alphafold Metacentrum job` template to configure your job.


## Running Alphafold in Kubernetes

AlphaFold can be run on a [Kubernetes](https://docs.cerit.io) platform for users requiring additional flexibility. This approach offers access to [Foldify](https://docs.cerit.io/en/web-apps/foldify), a web-based graphical environment built around AlphaFold. Foldify provides a suite of tools, including:

 * AlphaFold2
 * ColabFold
 * OmegaFold
 * ESMFold




## Running Alphafold as Singularity image in Remote desktop 

Using [Remote desktop](../../../software/graphical-access), AlphaFold can be also run from a [Singularity](../../../software/containers) image.

This option is recommended to advanced users or as a fallback option in case OnDemand and/or Kubernetes service are down.

This package provides an implementation of the inference pipeline of AlphaFold v2.1.1 This is a completely new model that was entered in CASP14 and published in Nature. For simplicity, we refer to this model as AlphaFold throughout the rest of this document. 

Application is prepared as [Singularity](../../../software/containers) image. The image, together with databases and example scripts are available at

    /storage/brno11-elixir/projects/alphafold 

There are four models with two speed/quality tradeoff. All combinations of these parameters are prepared in example scripts in Metacentrum.

**CUDA license**

To use Alphafold with CUDA, you will also need to accept license for cuDNN library. You will find the link on [MetaVO licence pages](https://metavo.metacentrum.cz/cs/myaccount/licence.html).

**Models**

You can control which AlphaFold model to run by adding the `--model_preset= flag`. We provide the following models:

- `monomer`: This is the original model used at CASP14 with no ensembling.
- `monomer_casp14`: This is the original model used at CASP14 with `num_ensemble=8`, matching our CASP14 configuration. This is largely provided for reproducibility as it is 8x more computationally expensive for limited accuracy gain (+0.1 average GDT gain on CASP14 domains).
- `monomer_ptm`: This is the original CASP14 model fine tuned with the pTM head, providing a pairwise confidence measure. It is slightly less accurate than the normal monomer model.
- `multimer`: This is the AlphaFold-Multimer model. To use this model, provide a multi-sequence FASTA file. In addition, the UniProt database should have been downloaded.

**Speed/Quality**

You can control MSA speed/quality tradeoff by adding `--db_preset=reduced_dbs` or `--db_preset=full_dbs` to the run command. We provide the following presets:

- `reduced_dbs`: This preset is optimized for speed and lower hardware requirements. It runs with a reduced version of the BFD database. It requires 8 CPU cores (vCPUs), 8 GB of RAM, and 600 GB of disk space.
- `full_dbs`: This runs with all genetic databases used at CASP14.

**Tips and useful information**

Example of run with different models and speed/quality tradeoff with example file `seq.fasta`, multimer with `multi.fasta`. This test shows difference of RAM consuming a length of run with the same test.

| model | speed/quality | RAM | Duration | cluster - GPU |
|-----|-------|-------|-------|------|
|monomer 	|full_dbs 	|185 GB 	|28 min 	|glados - RTX2080 - 8GB |
|monomer 	|reduced_dbs 	|153 GB 	|36 min 	|glados - RTX2080 - 8GB |
|monomer_casp14 |full_dbs 	|197 GB 	|35 min 	|zia - A100 - 40GB |
|monomer_casp14 |reduced_dbs 	|38 GB 		|36 min 	|zia - A100 - 40GB |
|monomer_ptm 	|full_dbs 	|190 GB 	|36 min 	|gita - RTX2080 Ti - 11GB |
|monomer_ptm 	|reduced_dbs 	|55 GB 		|32 min 	|gita - RTX2080 Ti - 11GB |
|multimer 	|full_dbs 	|119 GB 	|75 min 	|zia - A100 - 40GB |
|multimer 	|reduced_dbs 	|40 GB 		|73 min 	|zia - A100 - 40GB |

