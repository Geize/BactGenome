## Bacterial genome assembly and prediction - snakemake

------------------------------------------------------------------------

Hi Folks! 😀

First thing first. Our mantra 🕉️ : This repository is not a tutorial. It is just for reproducing my work. However, you are more than welcome to use this workflow. And if you find any error, please, you'll welcome as well to complain (but not too much 😊). I'll be glad to fix it.

**The workflow will do:**

1.  Quality control of llumina MiSeq reads (paired-end reads, PE) - <a href="https://www.bioinformatics.babraham.ac.uk/projects/fastqc/">FastQC</a>.

2.  Trimmed the raw reads - <a href="http://www.usadellab.org/cms/?page=trimmomatic"> Trimmomatic</a>.

3.  Assembly the quality-filtered paired-end reads - De novo assembly - <a href="https://github.com/ablab/spades">SPAdes</a>.

4.  Quality assessment for evaluating genome assembled - <a href="https://quast.sourceforge.net">QUAST</a>.

5.  Detection chimera or contamination - <a href="https://grp-bork.embl-community.io/gunc/">GUNC</a>.

6.  Prediction and annotation - <a href="https://github.com/tseemann/prokka">Prokka</a>.

7.  Folders have the same name of each tool used.

**Important points:**

Create a folder named `reads/` and transfer your "fastq.gz" to this folder. Then, rename your "fastq.gz" files to `{dadada}_1.fastq.gz` and `{dadada}_2.fastq.gz`.

From my repository: download to your area the file with all PE sequence adapters in Adapter folder for trimming step, and GenomeAnalysis.yaml file in env folder to recreate the the same environment that I use to process my data.

`$ conda env create -n snake -f GenomeAnalysis.yaml`

`$ conda activate snake`

Now, everything is ready to run the workflow.

**Additional information:**🔥

SPAdes is still the best assembler for bacterial genome assembly (considering that you are using PE). That's why you won't find any another assembler as a second option. However, if you still want try with another assembler, it is very easy to add a new rule or replace the current one in the workflow (but, you'll be in charge to do it 😄).

QUAST - Gives an idea about how good your assembly is. But, QUAST was not set up for comparing genome assemblies. I guess you can easily have a better comparison going directly to the NCBI genome.

GUNC - This is a new tools for detecting and quantifying chimerism. In my opinion, it is better than CheckM.


**All the best for us.**
