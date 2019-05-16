# Technical Report
This report summaries the process, findings, and future work of my ongoing project to understand the relationship between linguistic diversity and biodiversity, to located high risk areas, and identify underlying causes.<br>

Currently, I have built three models with varying degrees of success:
1. Predicting continent origin of language from grammatical features.
2. Predicting endangered status from grammatical structure.
3. Predicting linguistic diversity index of countries based on demographic information.

Efforts to build models that incorporate biodiversity are ongoing.

## Directory Structure
```
.
├── 01_code
├── 02_data
├── 03_maps_and_images
└── README.md
```

## Data Sources

Data for this project was pull from a variety of sources:
- **Biodiversity Data:** The [Global Biodiversity Information Facility](https://www.gbif.org) has an incredibly rich of database of biodiversity information from thousands of datasets. All together it contains over one billion observations of individuals across all kingdoms of life with longitude and latitude and date of observation. This information can be filter by location, taxonomic information and various other criterion.
- **Demographic Data:** Demographic data was acquired from [United States Census Bureau](https://www.census.gov/en.html) [International Database](https://www.census.gov/data-tools/demo/idb/informationGateway.php) which has global demographic data dating back to 1950 and projected out to 2050.
- **Linguistic Data:** Linguistic data was pulled from the greatest variety of sources in order to acquire all the features of interest.
  - The [World Atlas of Languages (WALS)](https://wals.info/) contains a rich dataset with over 2,000 languages with grammatical features and links to academic articles elaboration the information.
  - The [United Nations Educational, Scientific and Cultural Organization (UNESCO)](http://www.unesco.org/) monitors endangered languages and relevant data in their [Atlas of the World's Languages in Danger](http://www.unesco.org/languages-atlas/index.php?hl=en&page=statistics). These findings were reported on in an [article](https://www.theguardian.com/news/datablog/2011/apr/15/language-extinct-endangered#data) by [The Guardian](https://www.theguardian.com/uk).
  - [Ethnologue](https://www.ethnologue.com/) is a regular publication with over 7,000 languages and population information about the speakers. It was sited by many of the above data sources.
  - Additional data was acquired from [The Joshua Project](https://joshuaproject.net/), an academic article entitled ["Global distribution and drivers of language extinction risk"](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4173687/) by Tatsuya Amano et al., and [Glottolog](https://glottolog.org/), but they have not yet been used in final analysis.

## Data Analysis and Processing

The [Capstone Explorer](./code/CapstoneExplorer.ipynb) is where I did my initial data cleaning and exploratory data analysis before creating topic specific notebooks and model specific notebooks.  

Topic Notebooks:
- The [Biodiversity Explorer](./code/BiodiversityExplorer.ipynb) notebook was used to clean and explore biodiversity data.
- The [Africa](./code/Africa.ipynb) notebook was used to look at linguistic, demographic, and biodiversity data of a more focused area.
- The [Languages](./code/Africa.ipynb) notebook was used to look at linguistic data and to do intitial modeling.
- The [Folium](./code/Folium.ipynb) notebook was used to create interactive maps.

Model Notebooks
-  The [World](./code/World.ipynb) notebook was used to build a model that used demographic information of countries to predict their linguistic diversity index.
- The [Languages](./code/Languages.ipynb) notebook was used to build two models. One that predicts continent origin of language from grammatical features and another that predicts endangered status from grammatical structure.
- The [Cluster](./code/Cluster.ipynb) notebook is being used to build a model that associates species clusters with languages.


## Modeling

The first model used grammatical features of languages to predict continent of origin. The model was able to predict with 82% accuracy on testing data. This is compatible with linguistic theories about the genetic relationships between Languages and reinforces the parallels between species and language diversification.

The second model attempted to predict the endangered status of languages based on their grammatical features. Various iterations consistently performed very poorly on testing data, indicating that based on this model there are not structural features of languages that predict survival rates.

The third model used demographic data to predict the linguistic diversity index for countries. Further analysis is needed to elucidate the specific relationship between the demographic data and the linguistic diversity. Specifically, this model used demographic information from a single year. I hope to incorporate time series data and demographic trends in future versions.

## Mapping

Beyond the quantitative results of the modeling, I wanted to display the information in the most useful format. I created a number of interactive maps using [Bokeh](https://bokeh.pydata.org/en/latest/) and [Folium](https://python-visualization.github.io/folium/). They can be found in the [03_maps_and_images](./03_maps_and_images) folder.


## Summary

This project has been incredibly rewarding even though I have barely begun to scratch the surface. So far I have built three models. Two provided predictive ability. One did not perform well on testing data.

The first model used grammatical features of languages to predict continent of origin. The model was able to predict with 82% accuracy on testing data. This is compatible with linguistic theories about the genetic relationships between Languages and reinforces the parallels between species and language diversification.

The second model attempted to predict the endangered status of languages based on their grammatical features. Various iterations consistently performed very poorly on testing data, indicating that based on this model there are not structural features of languages that predict survival rates.

The third model used demographic data to predict the linguistic diversity index for countries. Further analysis is needed to elucidate the specific relationship between the demographic data and the linguistic diversity. Specifically, this model used demographic information from a single year. I hope to incorporate time series data and demographic trends in future versions.

## Future Work

This is an ongoing project to understand the relationship between linguistic diversity and biodiversity, to located high risk areas, and identify underlying causes. Future modeling will further explore the relationships between linguistic diversity and biodiversity.

If you're interested in collaborating, feel free to [send me an email](mailto:micahluedtke@gmail.com).
