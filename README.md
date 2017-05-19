# UMI_doc
Documentation for tag based scRNA-Seq


## inDrop
Citation:<br/>
Cell. 2015 May 21;161(5):1187-201. doi: 10.1016/j.cell.2015.04.044.<br/>
Droplet barcoding for single-cell transcriptomics applied to embryonic stem cells.<br/>
Klein AM1, Mazutis L2, Akartuna I3, Tallapragada N1, Veres A4, Li V1, Peshkin L1, Weitz DA5, Kirschner MW6.<br/>
```
5'- /5Acryd/ /iSpPC/ CGATGACG TAATACGACTCACTATAGGG ATACCACCATGG CTCTTTCCCTACACGACGCTCTTC
         CGATCT [barcode1] AAGGCGTCACAAGCAATCACTC [barcode2] NNNNNN TTTTTTTTTTTTTTTTTTTV -3’
```
### Json:
```
{
    "read1": "(?P<name>[^\\s]+).*\\n(?P<CB>.{30})(?P<MB>.{6})(.*)\\n\\+(.*)\\n(.*)\\n",
    "read2": "(@.*)\\n(?P<seq>.*)\\n\\+(.*)\\n(?P<qual>.*)\\n"
}
```
<b>Data source:</b><br/>
https://www.ebi.ac.uk/arrayexpress/files/E-GEOD-65525/E-GEOD-65525.sdrf.txt<br/>


## Drop-Seq
Citation:<br/>
Cell. 2015 May 21;161(5):1202-14. doi: 10.1016/j.cell.2015.05.002.
Highly Parallel Genome-wide Expression Profiling of Individual Cells Using Nanoliter Droplets.
Macosko EZ1, Basu A2, Satija R3, Nemesh J4, Shekhar K5, Goldman M6, Tirosh I5, Bialas AR7, Kamitaki N4, Martersteck EM8, Trombetta JJ5, Weitz DA9, Sanes JR8, Shalek AK10, Regev A11, McCarroll SA12.
```
Barcoded Bead SeqA 5’ –Bead–Linker-TTTTTTTAAGCAGTGGTATCAACGCAGAGTACGTJJJJJJJJJJJJNNNNNNNN
TTTTTTTTTTTTTTTTTTTTTTTTTTTTTT-3’
Barcoded Bead SeqB 5’ –Bead–Linker-TTTTTTTAAGCAGTGGTATCAACGCAGAGTACJJJJJJJJJJJJNNNNNNNN
TTTTTTTTTTTTTTTTTTTTTTTTTTTTTT-3’
```
### Json:
```
{
    "read1": "(?P<name>[^\\s]+).*\\n(?P<CB>.{12})(?P<MB>.{8})(.*)\\n\\+(.*)\\n(.*)\\n",
    "read2": "(@.*)\\n(?P<seq>.*)\\n\\+(.*)\\n(?P<qual>.*)\\n"
}
```
<b>Data source:</b><br/>
https://www.ncbi.nlm.nih.gov/geo/download/?acc=GSE63473&format=file


## MARSeq
Citation:<br/>
Massively Parallel Single-Cell RNA-Seq for Marker-Free Decomposition of Tissues into Cell Types. Diego Adhemar Jaitin*, Ephraim Kenigsberg*, Hadas Keren-Shaul*, Naama Elefant, Franziska Paul, Irina Zaretsky, Alexander Mildner, Nadav Cohen, Steffen Jung, Amos Tanay, Ido Amit. Science 2014
```
FigS2
TableS7
CGATTGAGGCCGGTAATACGACTCACTATAGGGGCGACGTGT
GCTCTTCCGATCTXXXXXXNNNNTTTTTTTTTTTTTTTTTTTTN,
where XXXXXX is the cell barcode and NNNN is the RMT
```
### Json:
```
{
    "read1": "(?P<name>@.*).*:(?P<CB>.{6}):(?P<MB>.{4,8})\\n(?P<seq>.*)\\n\\+\\n(?P<qual>.*)\\n",
    "read2": null
}
```
<b>Data source:</b><br/>
http://www.wisdom.weizmann.ac.il/~effi/science2014/jaitin_etal_fastqs.tgz

