# Sam2TPM_RPKM

inputs: sample.sam, sample.gtf

Usage: 

1. place py in a directory with your sample.sam and sample.gtf
2. run with python (i.e $python Sam2tpm_rpkm.py)

How it works:

###Calculate TPM:
(X[i]/L[i])*(1/(sum(Xtot/Ltot)))*1e6
####breaking it down to steps:
1. Take each gene read and divide by length (in kb) of gene
2. Next take these normalized reads and sum them for each gene
3. create scaling factor by dividing summed normalized reads by 1e6
4. take your normalized reads from step 1 and divide by the scaling factor
 

####Taken from these websites:
Instructions from [here] (https://www.youtube.com/watch?v=TTUrtCY2k-w)
and [here] (https://haroldpimentel.wordpress.com/2014/05/08/what-the-fpkm-a-review-rna-seq-expression-units/)

###Calculate RPKM:
Mapped_Reads/((Total_reads/1000000) * (Lenth_Gene/1000))

#####Mapped_Reads is the reads that were mapped to a gene in the gtf file
#####Total_reads is the total reads in the experiment
#####Length of gene is in kb

1. Get number of reads
2. Calculate Number_of_reads/(length_of_gene/kilobase * total_number_reads/1e6)

Instructions found [here](https://haroldpimentel.wordpress.com/2014/05/08/what-the-fpkm-a-review-rna-seq-expression-units/)
