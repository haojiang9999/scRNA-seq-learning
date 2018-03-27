# scRNA-seq-learning
 Using STAR to create the index:由于内存小所以改用:
```
$ STAR  --runMode genomeGenerate --runThreadN 12 --genomeDir /home/huangrt/JH/Genome/indices/STAR --genomeFastaFiles  ./gencode.vM16.transcripts.fa --genomeSAindexNbases 12 --genomeChrBinNbits 14 --genomeSAsparseD 3
```
STAR Alignment
```
mkdir results
mkdir results/STAR

STAR --runThreadN 4 --genomeDir indices/STAR --readFilesIn Share/ERR522959_1.fastq Share/ERR522959_2.fastq --outFileNamePrefix results/STAR/
```
