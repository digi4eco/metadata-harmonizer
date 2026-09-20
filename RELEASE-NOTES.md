## Version 1.0.8 ##
1. Synced with the EMSO ERIC metadata-harmonizer development branch
2. Removed the EMSO-specific attributes `emso_site_name`, `emso_site_uri`, `emso_regional_facility_name`,
   `emso_regional_facility_uri`, `emso_platform_name` and `emso_platform_uri` from validation, generation and examples
3. Removed the `oso_ontology_name` / `oso_ontology_uri` compliance tests and the dead `emso_facility` /
   `emso_site_code` tests; dropped the `emso_facility` column from the metadata report
4. Specifications and vocabularies are now downloaded from the DIGI4ECO specifications repository
5. Renamed the local cache folder from `.emso` to `.digi4eco` and the package to `digi4eco_metadata_harmonizer`
6. Removed the PyPI packaging configuration, this fork is used from source

## Version 1.0.7 ##
1. Adding alternative download URI for EuroSciVoc, GCMD and GEMET vocabularies (EuroSciVoc automatic downloads have been forbidden as of 2026-06-25)

## Version 1.0.6 ##
1. Release with no changes (human error managing git release)

## Version 1.0.5 ##
1. Improved keyword management
2. adding `--clear` option to generator and metadata_report
3. fixing windows bug when writing gemet rdf file
4. The option `--csv` now creates a CSV file for every dataset (avoids overwrite)
5. The output report includes keywords and operational tests
6. Fixed examples, now they are almost 100% compliant (just missing AUVs definitions in OSO)

## Version 1.0.4 ##
1. Adding keyword checks 
2. Adding extensive keywords analysis with --keywords
3. Improved resource.json dependency download system

## version 1.0.3 ##
1. Parse copernicus vars as markdown
2. Support for time_end

 
## version 1.0.2 ##
1. Force URLs pointint to the specs dev branch, this avoid vocab updates without new Specs release
2. Implementing proper way to handle logs using digi4eco_metadata_harmonizer logger
3. Adding the CSV option to the metadata report, to store individual reports as CSV files

## version 1.0.1 ##
1. Fixing URLs pointing to develop branch
2. Improved README

## version 1.0 ##
1. Major modifications in all the project to adapt to the new metadata specifications
2. Using unique metadata YAML files instead of the old .min.json / .full.json files
3. Major changes in WaterFrame class
4. Adding operational tests to ensure data usage
5. Adding oso viewer
6. Adding 15 examples
7. Ensuring compatibility with Climate and Forecast

## version 0.4.7 ##
1. Adding multisensor metadata option to keep the sensor metadata sensors even if one of them has no data. 

## version 0.4.7 ##
1. Fixing errors that silently dropped rows when generating NetCDF files

## version 0.4.6 ##
1. Updating JSON-ld parser to match changes in SeaDataNet vocabs

## version 0.4.5 ##
1. Fixing threadify arguments
2. Fixing erddap_config arguments
3. Fixing 2CTDs examples README

## version 0.4.4 ##
1. Fixing inconsistencies with PyPi

## version 0.4.3 ##
1. Improved API to generate datasets, now can be called with dicts and DataFrames (before only with files)
2. Removing mooda dependencies (this time for sure)
3. Adding option to reuse Digi4ecoMetadata, speeding up creation of multiple datasets
4. Removing most prints to clear stout

## version 0.4.2 ##

**changes**:
1. Converter generator/reporter/erddap_config into callable functions (before it was only cli)
2. Packed and published project in pypi
3. Adding testing with unittests
4. Removed mooda and reimplemented a lightweight version of WaterFrame