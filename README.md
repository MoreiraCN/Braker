### Genomic annotation with Braker

The following pipeline was used for aligning protein sequences of *Mus musculus* to the assembled genome of the species *Holochilus sciureus* (2n = 56, NF = 56), a Neotropical rodent of tribe Oryzomyini.

**Software used:**

[Braker](https://github.com/Gaius-Augustus/BRAKER). Brůna T, Hoff KJ, Lomsadze A, Stanke M, Borodovsky M (2021) BRAKER2: Automatic eukaryotic genome annotation with GeneMark-EP+ and AUGUSTUS supported by a protein database. NAR Genom Bioinform, 3(1):lqaa108.

**Input data:**

- Softmasking genome, the genome masked with [RepeatMasker](https://github.com/MoreiraCN/RepeatMasker) using the option '-xsmall' in the comand line for masking (`/RepeatMasker perl -pa 20 -gff -xsmall -lib /repeatmodeler/sample_name/consensi.fa.classified -s -a -dir RepeatMasker_sample_name assembly.fa`).
- Protein translations of Ensembl genes from a [reference species](http://ftp.ensembl.org/pub/release-104/fasta/mus_musculus/pep/).

**Command line used:**

`/braker.pl --genome assembly.fa.masked --prot_seq Mus_musculus.GRCm39.pep.all.fa --prg gth --trainFromGth --softmasking --cores 12 --AUGUSTUS_CONFIG_PATH=/Augustus/config/`

**Parameters used:**

- All parameters used are available at [BRAKER User Guide](https://github.com/Gaius-Augustus/BRAKER).
