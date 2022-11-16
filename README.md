#### Bacterial genome assembly and prediction - snakemake

Hi Folks! 😀

First thing first.Our mantra 🕉️ : This repository is not a tutorial. It is just for reprocuding my work. However, you are more than welcome to use this workflow. And if you find any error, please, you'll welcome as well to complain (but not too much 😊). I'll be glad to fix it.

**The workflow will do:**

1.  Quality control of llumina MiSeq reads (paired-end reads, PE) - <a href="https://www.bioinformatics.babraham.ac.uk/projects/fastqc/">FastQC</a>.

2.  Trimmed the raw reads - Trimmomatic.

3.  Assembly the quality-filtered paired-end reads - De novo assembly - \<a href="<https://github.com/ablab/spades>"\>SPAdes</a>. 🔥

4.  Quality assessment for evaluating genome assembled - <a  href="https://quast.sourceforge.net">QUAST</a>. 🔥

5.  Detection chimera or contamination - <a href="https://grp-bork.embl-community.io/gunc/">GUNC</a>.🔥

6.  Prediction and annotation - <a href="https://github.com/tseemann/prokka">Prokka</a>.

7.  Folders have the same name of each tool used. (pretty 🤓)

**Important points:**🔥

Create a folder named `reads/` and transfer your "fastq.gz" to this folder. Then, rename your "fastq.gz" files to `{dadada}.1.fastq.gz` and `{dadada}.2.fastq.gz`.

From my repository: download to your area the file with all PE sequence adapters in Adapter folder for trimming step, and enomeAnalysis.yaml file to install/recreate the the same environment that I use to process my data.

`$ conda env create -n snake -f GenomeAnalysis.yaml`

`$ conda activate snake`

Now, everything is ready to run the workflow.

**Additional information:**🔥

SPAdes is still the best assembler for bacterial genomes (considering that you are using PE). That's why you won't find any another assembler as a second option. However, if you still want try with another assembler, it is very easy to add a new rule or replace the current one in the workflow (but, you'll be in charge to do it 😄).

QUAST - Gives an idea about how good your assembly is. But, it was not set up for comparing genome assemblies. I guess you can easily have a better comparison going directly to the NCBI genome.

GUNC - This is a new tools for detecting and quantifying chimerism. I guess it is better than CheckM.

The next two repository is dedicated to identify enzymes and reconstruct metabolic pathways, and phylogenomic analysis (be patient 🤓, coming soon 🏃‍♀️,).

**All the best for us.**

🤓
