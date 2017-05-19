# UMI_doc
Documentation for tag based scRNA-Seq

## inDrop
Citation:
Cell. 2015 May 21;161(5):1187-201. doi: 10.1016/j.cell.2015.04.044.
Droplet barcoding for single-cell transcriptomics applied to embryonic stem cells.
Klein AM1, Mazutis L2, Akartuna I3, Tallapragada N1, Veres A4, Li V1, Peshkin L1, Weitz DA5, Kirschner MW6.

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
