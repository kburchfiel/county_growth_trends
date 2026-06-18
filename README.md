# County Growth Trends

By Ken Burchfiel

Released under the MIT License

[Click here](https://kburchfiel.github.io/county_growth_trends/county_growth_map.html) to view the population-growth dashboard stored within this repository.

*Note: I did not use generative AI tools to create this project.*

I often find that quantile-based scales work better than linear ones when visualizing choropleth map data. (After all, particularly high or low values can easily skew a linear range.)

Therefore, I put together a county-population-growth dashboard that allows growth rates to be viewed in either percentile-based or quantile-based form. The dashboard also lets users determine the starting and ending years for population growth calculations *and* set a minimum population size; the dashboard’s JavaScript code will then calculate new colorscales accordingly.

The dashboard also shows how to use Plotly.js's `hovertemplate` and `customdata` arguments to create custom tooltips that show data both from the map’s underlying GeoJSON data and the population-growth table that it imports.

Although I’ve enjoyed using Danfo.js for underlying data manipulation, that library hasn’t been updated in a little while, so I used d3-array for certain data-related tasks instead.

## Updates

* 2026-06-16: Percentile-rank calculations are now performed far more quickly. In addition, the dashboard now displays an error message if an excessively-high minimum-county-population value is requested.

* 2026-06-09: 

    * I added rank and percentile-rank information to each region's tooltips. The percentile-rank-calculation code takes a little while to run, so I'll look into a faster option. 

    * I clarified that the chart shows changes across 5-year timeframes (as each ACS5 survey covers 5 years of data) rather than population values for single years.

* 2026-06-17:

    * I replaced the continuous colorscale used in the original map with a categorical scale. This involved assigning bin labels to each row, then adding each label's corresponding regions to the map within a for loop. This approach simpler than the original setup *and* allows users to show or hide bins of their choice within the dashboard. (Note: The original map, which does render a little more quickly, is still available at https://github.com/kburchfiel/county_growth_trends/county_growth_map_continuous_colorscale.html .)

## Potential future updates

1. Add data for additional years as it becomes available

2. Prevent users from choosing an ending year that is less than or equal to the starting year
 
## Screenshots

Default view: ![](Screenshots/default_view.png)

Filtered view showing only counties with 100K+ residents in 2024: ![](Screenshots/filtered_view.png)

Linear scale: ![](Screenshots/linear_scale.png)