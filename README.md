# Metadata Harmonizer #
This python project contains the tools to generate NetCDF datasets following the [DIGI4ECO Metadata Specifications](https://github.com/digi4eco/digi4eco-metadata-specifications). It contains a set of software tools that help users to create NetCDF datasets, integrate them into ERDDAP and ensure that they are compliant with the metadata specifictaions. This repository also includes a detailed set of examples on how to create NetCDF datasets in a wide variety of fixed and mobile platforms.

Tools included in this repository:

* **generator.py**: Creates NetCDF datasets from simple CSV and YAML files. The CSV files are used as data input and the YAML files are used as metadata input.
* **erddap_config.py**: Integrates NetCDF files as a new dataset in an ERDDAP server.
* **metadata_report.py**: Checks the metadata from an ERDDAP dataset or NetCDF file and provides a harmonization score with some tips to improve the metadata records.


## Prerequisities ##
To use this repository you need a computer with `python3`, `pip` and `git`. Linux is strongly recommended. To install them using apt cli interface (ubuntu):
```bash
sudo apt install python3 python3-pip git -y
```


## Setup this project ##
1. Download this repository:
```bash
git clone https://github.com/digi4eco/metadata-harmonizer
```

2. Enter the folder with the source code
```bash
cd metadata-harmonizer
```
3. Install dependencies
```bash
pip3 install -r requirements.txt
```
## Dataset Generator ##
This tools takes data in CSV and metadata in YAML files and packs them together into a standardized NetCDF file. In the [examples folder](https://github.com/digi4eco/metadata-harmonizer/tree/main/examples) several example datasets with synthetic data. It uses the following syntax:

```bash
python3 generator.py --data <CSV files> --metadata <YAML files> [--output <output netcdf file>]
```
Where:
* `--data`: List of CSV files
* `--metadata`: List of YAML files with metadata
* `--output`: (optional): Output NetCDF file

The `--data` and the `--metadata` arguments are mandatory. If `--output` is not provided, the resulting dataset will be stored in `out.nc`. 
For instance, to create a dataset with the example 01:

```bash
python3 generator.py --data examples/01/*.csv --metadata examples/01/*.yaml --output example01.nc
```

## ERDDAP Auto-configurator ##
This tools takes a previously generated NetCDF dataset and automatically integrates it into an ERDDAP server. It can provide the `datasets.xml` chunk to include the dataset, or it can directly modify the `datasets.xml` file if it is passed with the `--xml` argument. It uses the following syntax:


```bash
python3 erddap_config.py <file> <dataset_id> <source> [--xml]
```
Where:
* `file`: NetCDF file where the metadata will be read
* `dataset_id`: Identifier to be assigned to the ERDDAP dataset
* `source`: path where the ERDDAP server will find the NetCDF files.
* `--xml`: (optional) Path to the ERDDAP `datasets.xml` file to automatically integrate the dataset.

⚠️ WARNING: When using docker containers,  for `source` the path inside the container must be used! Make sure to use the [docker volumes](https://docs.docker.com/engine/storage/volumes/) destination path. 


## Metadata Report ##

The `metadata_report.py` tool tests if the metadata contained within a dataset (ERDDAP, NetCDF or JSON) is compatible with DIGI4ECO Metadata Specifications.

To test an erddap dataset:
```bash
$ python3 metadata_report.py <erddap url>  --list  # get the list of datasets
$ python3 metadata_report.py <erddap url>  -d <dataset_id>  # Run the test for one dataset
```

For example, to run tests on dataset with id=```Western_Ionian_Sea_CTD_2002_2003``` from DIGI4ECO's central ERDDAP:
```bash
$ python3 metadata_report.py https://erddap.digi4eco.eu -d Western_Ionian_Sea_CTD_2002_2003
```
    
To run tests on all ERDDAP datasets:
```bash
$ python3 metadata_report.py <erddap url> 
```
To run tests on a NetCDF file
```bash
$ python3 metadata_report.py <filename> 
```

### Contact info ###

* **author**: Enoc Martínez  
* **version**: v0.1
* **organization**: Universitat Politècnica de Catalunya (UPC)    
* **contact**: enoc.martinez@upc.edu  
