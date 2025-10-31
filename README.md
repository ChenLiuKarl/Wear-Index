This script is for generating wear index report for routes. In the first version, the inputs are only origin and destination postcodes. The route is generated automatically and a wear index report is generated based on the route.

The report now contains four basic numbers: route distance, total wear for 6 tyres, average wear index per km, and equivalent wear of tread depth per 1000km on each tyre. In addition, a map of the route and markers of where wear happens is added.

In the script, the main function calls the function 'wear_index' for calculation. The flow of the script is as follow: 

1. The postcodes are parsed using function 'geocode'.
2. Route is generated using function 'compute_route'.
3. Coordinates and distance are calculated from the route using function 'route_info_to_meter'.
4. The coordinates are resampled for constant speed simulation using function 'resample_curve_fixed_step'.
5. Turns in the route where wear happens are extracted using function 'extract_sections'.
6. The sections extracted are simulated for wear index using function 'stitch_simulation'.
7. The calculation results are used for report generation using function 'generate_report'.

For wear calculation on a single tyre, there are two models to choose: an empirical model based on slip angle and load, and a surrogate model derived from a tyre-road contact model. 
The vehicle dynamics simulation in the script is based on a 6-wheel semi-trailer with 385/65R22.5 tyres.
The details can be refered to Liu, C. (2024). Investigation of Severe Abrasive Truck Tyre Wear (https://doi.org/10.17863/CAM.111100).
