DPSleep Pipeline Step #7 (upact - Update Sleep Parameters after QC)
=========
[![build status](https://ncfcode.rc.fas.harvard.edu/phoenix/upact/badges/master/build.svg)](https://ncfcode.rc.fas.harvard.edu/phoenix/upact/commits/master)

## Table of contents
1. [Requirements](#requirements)
2. [Usage examples](#usage-examples)

### Requirements
- Run this step after doing Quality Control and saving the csv file with adding "_qcd" to the name
To run the upact pipeline, users may choose one of the following options:

##### Option 1 - Installation

To install Stopwatch on your system, run the following commands:
```bash
git clone git@ncfcode.rc.fas.harvard.edu:phoenix/upact .
cd upact
pip install -r requirements.txt
```

##### Option 2 - Module Load (Within NCF only)

To load UPACT module on NCF without an installation:
```bash
module load miniconda3
module load matlab/R2017a-fasrc01
module load upact/master-ncf
```

### Usage examples

```bash
# To generate reports under every subject's processed directory in PHOENIX
geneactiv_upact.py --data-type actigraphy --pipeline geneactiv_upact --data-dir GENERAL

# To generate reports for every subject and save them in ~/dp_test1 directory
geneactiv_upact.py --output-dir ~/dp_test1 --data-type actigraphy --pipeline geneactiv_upact --data-dir GENERAL
# or
geneactiv_upact.py --output-dir ~/dp_test1/ --data-type actigraphy --pipeline geneactiv_upact --data-dir GENERAL

# To generate reports for STUDY_A's subject B under ~/dp_test1 directory
geneactiv_upact.py --output-dir ~/dp_test1/ --study STUDY_A --subject B --data-type actigraphy --pipeline geneactiv_upact --data-dir GENERAL

# To generate reports for subject A and subject C in STUDY_PILOT under their processed folders
geneactiv_upact.py --study STUDY_PILOT --subject A C --data-type actigraphy --pipeline geneactiv_upact --data-dir GENERAL

# To generate reports for subject A and subject C in STUDY_PILOT under their processed folders
# Define the PHOENIX, consent and MATLAB directories 
geneactiv_upact.py --study STUDY_PILOT --phoenix-dir /data/PHOENIX --consent-dir /data/PHOENIX/GENERAL --mtl-dir MATLAB_DIRECTORY --subject A C --data-type actigraphy --pipeline geneactiv_upact --data-dir GENERAL
```

#### For more information, please run:
```bash
geneactiv_upact.py -h
```
