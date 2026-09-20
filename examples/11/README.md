###  Example 11: Fish detections from underwater pictures, compatible with Darwin Core    
Fish detections from an underwater pictures analyzed through an object detection and classification algorithm trained to classify fish    
  
**sensors**: IPC608 underwater camera    
**platforms**: OBSEA Seafloor Observatory    
  
NetCDF generation command:  
```bash
python3 generator.py -m examples/11/*.yaml -d examples/11/*.csv --out example11.nc  
```
  
ERDDAP configuration:  
```bash
python3 erddap_config.py example11.nc example11 /path/to/nc/files 
```
  
  
**Additional info**:  
* 📂 [Explore the source files](https://github.com/digi4eco/metadata-harmonizer/tree/main/examples/./11)  
* 🔗 [ERDDAP dataset](https://netcdf-dev.obsea.es/erddap/tabledap/./11.html)  
