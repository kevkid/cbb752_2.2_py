# Sam2TPM_RPKM

inputs: sample.sam, sample.gtf

Usage: 

1. place py in a directory with your sample.sam and sample.gtf
2. run with python (i.e $python Sam2tpm_rpkm.py)

How it works:

###Calculate TPM:
![(X[i]/L[i])*(1/(sum(Xtot/Ltot)))*1e6](https://s0.wp.com/latex.php?latex=%5Ctext%7BTPM%7D_i+%3D+%5Cdfrac%7BX_i%7D%7B%5Cwidetilde%7Bl%7D_i%7D+%5Ccdot+%5Cleft%28+%5Cdfrac%7B1%7D%7B%5Csum_j+%5Cdfrac%7BX_j%7D%7B%5Cwidetilde%7Bl%7D_j%7D%7D+%5Cright%29+%5Ccdot+10%5E6&bg=ffffff&fg=000000&s=0)

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
![Mapped_Reads/((Total_reads/1000000) * (Lenth_Gene/1000))](https://s0.wp.com/latex.php?latex=%5Ctext%7BFPKM%7D_i+%3D+%5Cdfrac%7BX_i%7D%7B+%5Cleft%28%5Cdfrac%7B%5Cwidetilde%7Bl%7D_i%7D%7B10%5E3%7D%5Cright%29+%5Cleft%28+%5Cdfrac%7BN%7D%7B10%5E6%7D+%5Cright%29%7D+%3D+%5Cdfrac%7BX_i%7D%7B%5Cwidetilde%7Bl%7D_i+N%7D+%5Ccdot+10%5E9++&bg=ffffff&fg=000000&s=0)

Mapped_Reads/((Total_reads/1000000) * (Lenth_Gene/1000))

#####Mapped_Reads is the reads that were mapped to a gene in the gtf file
#####Total_reads is the total reads in the experiment
#####Length of gene is in kb

1. Get number of reads
2. Calculate Number_of_reads/(length_of_gene/kilobase * total_number_reads/1e6)

Instructions found [here](https://haroldpimentel.wordpress.com/2014/05/08/what-the-fpkm-a-review-rna-seq-expression-units/)
