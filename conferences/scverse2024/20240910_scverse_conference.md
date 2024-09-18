# SCVERSE Conference 2024

Notes on scverse conference 2024 in Munich 
The conference was held on 10-12 September 2024 in Munich. 

<img src="images/title.jpeg" width="1000">

## First Day

### 1. What is new @scverse
1. Scanpy 2.0 will have dask, more speed, and better implementation of knn methods.

### 2. Upstream of the single-cell data deluge: On the importance of accurate, efficient, and open methods for preprocessing single-cell data 
**Rob Patro** (University of Maryland) 

1. preprocessing matters: [paper](https://www.biorxiv.org/content/10.1101/2024.08.10.607413v1.full) 

    * Tremendous degree of variation between which barcodes are called, and the corresponding expression assigned to genes. 
    * This variation also varies between datasets and organisms. 

2. CellRanger only outputs genes/lncRNAs 

3. Alevin-fry will output -> spliced, unspliced, and ambiguous count matrices ([GitHub](https://github.com/COMBINE-lab/alevin-fry))
    * It uses transcriptome as reference. 
    * It index both spliced and unspliced transcriptome. 
    * It corrects cell barcodes: 
        * First get the barcodes with 100% assurance 
        * Then check again the whitelist and if possible correct the barcode and if not remove the barcode 
    * It is fast and memory friendly (less than 4GB memory for 10X 2020A reference) 

4. Simpleaf is the simple af version of alevin-fry ([GitHub](https://github.com/COMBINE-lab/simpleaf)) 
    * It is aware of context and semantics of running alevin-fry 
    * It propagates important metadata through analysis 
    * Allows tracking data provenance (what reference and what tool were used) 
    * Improves reproducibility 

5. Do not use processed matrices unless you are sure about data provenance: 
    * What was the data 
    * What was the reference 
    * How was it processed 
    * Which tools 
    * Which versions 

6. Data provenance is important. 
    * What has Rob did? 
        * Tximport imports transcripts abundance with metadata 

7. QC tools:
    * AlevinQC is a biocondactor app (shiny version is available)
    * Alevin-fryQC is under development (beta version is available) 

8. Articles to read in this section: 
    * [Alevin-fry](https://www.nature.com/articles/s41592-022-01408-3) 
    * [simpleaf](https://academic.oup.com/bioinformatics/article/39/10/btad614/7295550) 
    * [Single-cell best practice](https://www.nature.com/articles/s41576-023-00586-w) 