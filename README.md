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
produce the Kallisto index.
```
mkdir indices/Kallisto
kallisto index -i /home/huangrt/JH/Genome/indices/Kallisto/transcripts.idx /home/huangrt/JH/Genome/indices/STAR/gencode.vM16.transcripts.fa
```
Solution to Kallisto  [Pseudo-Alignment](https://pachterlab.github.io/kallisto/manual)
```
mkdir results/Kallisto
kallisto pseudo -i /home/huangrt/JH/Genome/indices/Kallisto/transcripts.idx -o ./results/Kallisto
