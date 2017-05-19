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
         
fq1:
@SRR1784310.1 1/1
GCTTACNTGAGTGATTGCTTGTNACGCCTACCTTCTTGTATCCTTTTTTTT
+
AAAAAF#FFFFFFFFFFFFFFF#7FFFFFFFFFFFFFFFFFFFFFF7<FFF

fq2:
@SRR1784310.1 1/2
AAAAAAAAAGGATACAAGAAGGTAGGCGTCACAAGCAAT
+
AAAAAFAFFFFFFFFFAFFFFFFAFFFAF<.FFF7)F)F
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

fq1:

fq2:


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


## BATseq
Citation:<br/>
Mol Syst Biol. 2015 Jun 3;11(6):812. doi: 10.15252/msb.20156198.
Single-cell polyadenylation site mapping reveals 3' isoform choice variability.
Velten L1, Anders S1, Pekowska A1, Järvelin AI1, Huber W1, Pelechano V1, Steinmetz LM2.
```
Fig1

```
### Json:
```
{
    "read1": "(@.*)\\n(?P<MB>.{8})(.*)\\n\\+\\n(.*)\\n",
    "read2": "(?P<name>@.*) .*\\n(?P<seq>.*)\\n\\+\\n(?P<qual>.*)\\n"
}
```
<b>Data source:</b><br/>

## CEL-Seq
Citation:<br/>
Cell Rep. 2012 Sep 27;2(3):666-73. doi: 10.1016/j.celrep.2012.08.003. Epub 2012 Aug 30.
CEL-Seq: single-cell RNA-Seq by multiplexed linear amplification.
Hashimshony T1, Wagner F, Sher N, Yanai I.

Genome Biol. 2016 Apr 28;17:77. doi: 10.1186/s13059-016-0938-8.
CEL-Seq2: sensitive highly-multiplexed single-cell RNA-Seq.
Hashimshony T1, Senderovich N1, Avital G1, Klochendler A2, de Leeuw Y1, Anavy L1, Gennert D3,4,5, Li S6, Livak KJ6, Rozenblatt-Rosen O3,4,5, Dor Y2, Regev A3,4,5, Yanai I7.
```

```
### Json:
```
{
    "read1": "(?P<name>@.*) .*\\n(?P<CB>.{8})(?P<MB>.{4})(.*)\\n\\+(.*)\\n(.*)\\n",
    "read2": "(@.*)\\n(?P<seq>.*)\\n\\+(.*)\\n(?P<qual>.*)\\n"
}
```
<b>Data source:</b><br/>

## STRT-Seq
Citation:<br/>
Genome Res. 2011 Jul;21(7):1160-7. doi: 10.1101/gr.110882.110. Epub 2011 May 4.
Characterization of the single-cell transcriptional landscape by highly multiplex RNA-seq.
Islam S1, Kjällquist U, Moliner A, Zajac P, Fan JB, Lönnerberg P, Linnarsson S.
```

```
### Json:
```
dual index:
{
    "read1": "(?P<name>[^\\s]+).*\\n(?P<CB1>.{3})(?P<MB>.{5})(?P<G>G{3,3})(?P<seq>.*)\\n\\+(.*)\\n(.{3})(.{5})(.{3,3})(?P<qual>.*)\\n",
    "read2": "(@.*)\\n(?P<CB2>.*)\\n\\+(.*)\\n(.*)\\n"
}
SRP022764
{
    "read1": "(?P<name>[^\\s]+).*\\n(?P<MB>.{5})(?P<seq>.*)\\n\\+(.*)\\n(.{5})(?P<qual>.*)\\n",
    "read2": null
}
SRP045452
{
    "read1": "(?P<name>[^\\s]+).*\\n(?P<MB>.{6})(?P<G>G{3,3})(?P<seq>.*)\\n\\+(.*)\\n(.{6})(.{3,3})(?P<qual>.*)\\n",
    "read2": null
}
```
<b>Data source:</b><br/>

