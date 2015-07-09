#### KEGG-Annotation
#### The purpose of this repository is to describe a simple script of KEGG annotation of AA sequence files
-
- First, deploy the KOBAS and Uniprot databses for blast, usearch, and diamond

##### Uniprot/Swissprot

```
cd /data/DATABASES
mkdir UNIPROT
cd UNIPROT
wget ftp://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/uniprot_sprot.fasta.gz
gunzip uniprot_sprot.fasta.gz
```

- MAKE USEARCH DATABASE
```
usearch -makeudb_usearch uniprot_sprot.fasta -output uniprot.udb
```
- MAKE BLASTABLE DATABAESE
```
makeblastdb -in uniprot_sprot.fasta -input_type fasta -out uniprot_sprot -dbtype prot
```
- MAKE DIAMOND DATABASE
```
diamond makedb --in uniprot_sprot.fasta -d uniprot_sprot.diamond.db
```
- Give everyone permission
```
sudo chown bwawrik:mgmic *
sudo chmod 775 *
```


