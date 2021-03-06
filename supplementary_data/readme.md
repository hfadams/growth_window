# Chlorophyll-*a* growth window dataset: supplementary files
This folder contains source files used to generate the growth window dataset. *lake\_name\_formatting.csv* and *all_lake_coordinates.csv* files are used for generating the growth window dataset, in addition to the daily mean *in situ* water quality data, which can be found in the [FRDR repository]() along with the growth window dataset.

## Folder directory
* [lake_name_formatting.csv](https://github.com/hfadams/growth_window/blob/662c87faba3d5bd954d160357da87cf4741a9d4c/data/supplementary%20_data/lake_name_formatting.csv): conversion of lake names from original sampling location ID to name in the growth window dataset
* [all\_lake\_coords.csv](https://github.com/hfadams/growth_window/blob/ac46b91a203430bf76440d42d7880bbb072b425e/supplementary_data/all_lake_coordinates.csv): list of coordinates for all lakes in the dataset, used in the growth window calculation scripts. Coordinates were collected from the original data files or searched within the database where possible, otherwise they were estimated based on sampling location name.

## Dataset summary
The growth window dataset consists of 3137 rows of unique growth windows with 42 variables/ lake and SSR station parameters. There are 357 lake sampling locations and 30 paired SSR stations ≥ 40°N, monitored between 1964-2019.

## Variable descriptions

| Variable                          | Units                                                | Description                                                                                                                                                                                                                                                                                    |
|-----------------------------------|------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| lake                              | NA                                                   | Lake name, reformatted from original file                                                                                                                                                                                                     						    |
| lake_lat                          | decimal degrees                                      | lake latitude, collected from original data files and HydroLakes data  																											    |
| lake_long                         | decimal degrees                                      | lake longitude, collected from original data files and HydroLakes data 																											    |
| tsi                               | Range from 0-100                                     | Calculated from mean chlorophyll-*a* concentration across all years the lake was sampled, based on guidelines from the [North American Lake Management Society](https://www.nalms.org/secchidipin/monitoring-methods/trophic-state-equations/)  						    |
| trophic_status                    | oligotrophic, mesotrophic, eutrophic, hypereutrophic | Assigned using lake trophic status index <br/> **TSI ranges:** <br/> < 30 = oligotrophic <br/> 30-50 = mesotrophic <br/> 50-60 = eutrophic <br/> > 60 = hypereutrophic   															    |
| climate_zone                      | NA                                                   | Climate zone of the region where the lake is sampled, assigned using the HydroATLAS database <br/> **climate zones** <br/> 6 = Extremely cold and mesic <br/> 7 = Cold and mesic <br/> 8 = Cool, temperate, and dry <br/> 9 = Cool, temperate, and xeric <br/> 10 = Warm, temperate, and mesic |
| lake_elev                         | m above sea level                                    | Elevation of the lake, extracted from the [Global Multi-resolution Terrain Elevation Data (GMTED2010)](https://www.usgs.gov/core-science-systems/eros/coastal-changes-and-impacts/gmted2010?qt-science_support_page_related_con=0#qt-science_support_page_related_con) model                   |
| lake_area                         | km<sup>2                                             | Total lake surface area, extracted from the HydroLAKES database       																											    |
| lake_volume                       | m<sup>3                                              | Total lake volume, extracted from the HydroLAKES database                  																										    |
| mean\_lake\_depth                 | m                                                    | Mean lake depth, extracted from the HydroLAKES database                 																											    |
| year                              | integer                                              | Year the growth period occurred            																														    |
| season                            | spring, summer, single                               | Time of year when the growth window is detected 																														    |
| num_samples                       | integer                                              | Number of days sampled that year, can be used to filter the dataset        																										    |
| start_day                         | Day of year (1-365)                                  | Day of year that the growth window begins  																														    |
| end_day                           | Day of year (1-365)                                  | Day of year that the growth window ends   																															    |
| growth\_window\_length            | days                                                 | Duration of the growth window, including the start and end dates       																											    |
| chla_rate                         | µgL<sup>-1</sup>day<sup>-1                           | rate of increase in chlorophyll-*a* concentration during the growth window   																										    |
| max_chla                          | µgL<sup>-1                                           | Maximum chlorophyll-*a* concentration reached during the growth window   																											    |
| acc_chla                          | µgL<sup>-1                                           | Accumulated chlorophyll-*a* over the growth window, calculated using the numpy.trapz function   																								    |
| specific_chla_rate                | day<sup>-1                                           | chla_rate rate divided by initial concentration																														    |
| temp_corrected_specific_chla_rate | day<sup>-1                                           | Specific chlorophyll-*a* rate corrected for the influence of temperature using the equation from [Rosso et al (1995)](https://journals.asm.org/doi/abs/10.1128/aem.61.2.610-616.1995)*    													    |
| poc_rate                          | mgL<sup>-1                                           | Rate of increase or decrease in particulate organic carbon  from the start to the end of the growth window    																						    |
| chla_to_poc                       | mg chl-*a* : mg POC                                  | Rate of change in chlorophyll-*a* in proportion to particulate organic carbon during the growth window           																						    |
| gw_temp                           | °C                                                   | Mean surface water temperature during the growth window                      																										    |
| gw_tp                             | mgL<sup>-1                                           | Mean total phosphorus during the growth window 																														    |
| gw_secchi                         | m                                                    | Mean Secchi depth during the growth window    																														    |
| gw_ph                             | pH units                                             | Mean pH during the growth window              																														    |
| gw_srp                            | mgL<sup>-1                                           | Mean soluble reactive phosphorus during the growth window             																											    |
| gw_tkn                            | mgL<sup>-1                                           | Mean total Kjeldahl nitrogen during the growth window                     																											    |
| pre_gw_temp                       | °C                                                   | Mean surface water temperature during the 14 days leading up to the growth window  																									    |
| pre_gw_tp                         | mgL<sup>-1                                           | Mean total phosphorus during the 14 days leading up to the growth window     																										    |
| pre_gw_tkn                        | mgL<sup>-1                                           | Mean total Kjeldahl nitrogen during the 14 days leading up to the growth window 																										    |
| ssr_station**                     | NA                                                   | Station name as assigned in original database                                                                                                                                                                                                                                                  |
| ssr_id**                          | NA                                                   | ID number in original database (where available)                                                                                                                                                                                                                                               |
| ssr_id_type**                     | NA                                                   | Type of ID number (i.e., GEBA, Internal)  																															    |
| ssr_lat                           | decimal degrees                                      | SSR station latitude (sampling location)                                                                                                                                                                                                                                                       |
| ssr_long                          | decimal degrees                                      | SSR station longitude (sampling location) 																															    |
| geo_dist_km                       | km                                                   | Geodic distance between the paired lake and SSR station                    																										    |
| ssr_elev                          | m above sea level                                    | Elevation of the SSR station, extracted from the [Global Multi-resolution Terrain Elevation Data (GMTED2010)](https://www.usgs.gov/core-science-systems/eros/coastal-changes-and-impacts/gmted2010?qt-science_support_page_related_con=0#qt-science_support_page_related_con) model            |
| ssr_lake_elev_diff                | m                                                    | Difference in elevation between the paired lake ans SSR station            																										    |
| gw_ssr                            | Wm<sup>-2                                            | Mean solar radiation during the growth window 																														    |
| pre_gw_mean_ssr                   | Wm<sup>-2                                            | Mean solar radiation during the 14 days leading up to the growth window   																									        	    |                                                                                                                                                                                                                   

*calculation used for temperature correction:

		group.loc[:, 'f_temp'] = (mean_temp - t_max) * (mean_temp - t_min) ** 2 / ((t_opt - t_min) * ((t_opt - t_min) * (mean_temp - t_opt) - (t_opt - t_max) * (t_opt + t_min - 2 * mean_temp)))

        # divide specific growth rate by f_temp
        group.loc[:, 'temp_corrected_specific_chla_rate'] = group.loc[:, 'specific_chla_rate'] / group.loc[:, 'f_temp']

** see ssr\_data\_sources.csv in the associated FRDR repository for more information

## Additional documentation
HydroATLAS technical document and shapefile download is available through the [Hydrosheds HydroATLAS webpage](https://hydrosheds.org/page/hydroatlas).

HydroLAKES technical document and shapefile download is available through the [Hydrosheds HydroLAKES webpage](https://hydrosheds.org/page/hydrolakes) (includes more information regarding climate zone codes)

## References

Linke, S., Lehner, B., Ouellet Dallaire, C., Ariwi, J., Grill, G., Anand, M., … Thieme, M. (2019). Global hydro-environmental sub-basin and river reach characteristics at high spatial resolution. Scientific Data, 6(1), 1–15. [https://doi.org/10.1038/s41597-019-0300-6](https://doi.org/10.1038/s41597-019-0300-6)

Messager, M. L., Lehner, B., Grill, G., Nedeva, I., & Schmitt, O. (2016). Estimating the volume and age of water stored in global lakes using a geo-statistical approach. Nature Communications, 7, 1–11. [https://doi.org/10.1038/ncomms13603](https://doi.org/10.1038/ncomms13603)

