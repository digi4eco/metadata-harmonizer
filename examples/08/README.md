###  Example 08: AUV trajectory with a CTD    
AUV acquiring CTD data over a trajectory    
  
**sensors**: Sea-Bird Scientific SBE37 SMP CTD Sensor    
**platforms**: Girona 500 AUV SN0001    
  
NetCDF generation command:  
```bash
python3 generator.py -m examples/08/*.yaml -d examples/08/*.csv --out example08.nc  
```
  
ERDDAP configuration:  
```bash
python3 erddap_config.py example08.nc example08 /path/to/nc/files 
```
  
  
**Additional info**:  
* 📂 [Explore the source files](https://github.com/digi4eco/metadata-harmonizer/tree/main/examples/./08)  
* 🔗 [ERDDAP dataset](https://netcdf-dev.obsea.es/erddap/tabledap/./08.html)  
