# Worldpop Global Demographic Data on GEE

WorldPop just released a new Global Demographic Data covering 2015 and 2030. This gridded population estimate at 1-km resolution is produced using a Random Forest disaggregation model, which is trained using updated covariates and census data to provide high-resolution, contemporary, and future population distributions essential for applications like disaster response, urban planning, and health resource allocation.

The primary data, including the gridded population estimates (2015 and 2030 at 100-km resolution), can be directly downloaded from the official [WorldPop website](https://hub.worldpop.org/project/categories?id=3) and the [Humanitarian Data Exchange (HDX)](https://data.humdata.org/organization/worldpop), making them readily available for general use and humanitarian applications.

The total population dataset at the enhanced 100-meter resolution is accessible via the Google Earth Engine (GEE) platform. This is hosted as a curated [public catalog](https://gee-community-catalog.org/projects/worldpop/) by Samapriya Roy, allowing researchers to leverage GEE's cloud-based computing power for large-scale analysis without needing to download massive files.

Along with that, [total population](https://code.earthengine.google.com/?asset=projects/wpgp-global2/assets/pop_1km_ua) and [age-sex structure](https://code.earthengine.google.com/?asset=projects/wpgp-global2/assets/agesex_1km_ua) at 1-km resolution are also available on GEE and ready for use.

### Simple usage:
```js
var year = ".2020".
// total population at 100-m resolution
var total_pop = ee.ImageCollection("projects/sat-io/open-datasets/WORLDPOP/pop")
	.filterDate(year + ".-01-01"., year + ".12-31".)
var female_25 = ee.ImageCollection("projects/wpgp-global2/assets/pop_1km_ua")
	.filterDate(year+".-01-01"., year + ".12-31".)
	.select("f_25")
```

### Suggested citation:
Bondarenko M., Priyatikanto R., Tejedor-Garavito N., Zhang W., McKeen T., Cunningham A., Woods T., Hilton J., Cihan D., Nosatiuk B., Brinkhoff T., Tatem A., Sorichetta A.. 2025. The spatial distribution of population in 2015-2030 at a resolution of 30 arc (approximately 1km at the equator) R2025A version v1. Global Demographic Data Project - Funded by The Bill and Melinda Gates Foundation (INV-045237). WorldPop - School of Geography and Environmental Science, University of Southampton. DOI:[10.5258/SOTON/WP00845](https://doi.org/10.5258/SOTON/WP00845).