## Introduction

The Sustainable Development Goals (SDGs) are part of the UN 2030 Agenda for Sustainable Development. The Office for National Statistics (ONS) reports the UK data for the SDG indicators on the [UK SDG data website](https://sdgdata.gov.uk/).


Included in the 17 SDGs is Goal 15, which aims to ‘Protect, restore and promote sustainable use of terrestrial ecosystems, sustainably manage forests, combat desertification, and halt and reverse land degradation and halt biodiversity loss’. One of the goal 15 indicators that, until recently, remained unreported for the UK, is 15.1.2: ‘Proportion of important sites for terrestrial and freshwater biodiversity that are covered by protected areas, by ecosystem type’. 


This indicator shows temporal trends in the mean percentage of important sites for terrestrial and freshwater biodiversity that is covered by designated protected areas and Other Effective Area-based Conservation Measures (OECMs). Important sites for terrestrial and freshwater biodiversity are sites that contribute significantly to the global persistence of biodiversity. Throughout this document, these are referred to as Key Biodiversity Areas (KBAs).


Whilst there are now UK data available for this indicator on the International Biodiversity Assessment Tool (IBAT), these data are not disaggregated to country and region level within the UK. The methodology outlined below has therefore been used to report this indicator on the UK SDG data website at a more granular level. It should be noted that there are some differences in methodology between the two datasets. Most notably, the IBAT data do not currently include Important Plant Areas (IPAs) as Key Biodiversity Areas. In addition, the method of ecosystem type designation differs between the two datasets.


### Concepts:

#### Protected Areas
Protected areas, as defined by the International Union for Conservation of Nature (IUCN; Dudley 2008), are clearly defined geographical spaces, recognized, dedicated, and managed, through legal or other effective means, to achieve the long-term conservation of nature with associated ecosystem services and cultural values.


A protected area acquires the ‘designated’ status when the corresponding authority, according to national legislation or common practice (e.g., by means of an executive decree or the like), officially endorses a document of designation.


#### Key Biodiversity Areas (KBAs)

KBAs or Important Sites for Terrestrial and Freshwater Biodiversity are sites contributing significantly to the global persistence of biodiversity. KBAs are identified following global criteria set out in A Global Standard for the Identification of Key Biodiversity Areas (KBAs) (IUCN 2016) applied at national levels. KBAs encompass Important Bird and Biodiversity Areas (IBAs), Important Plant Areas (IPAs), Alliance for Zero Extinction sites (AZEs). 

## Data

**1.	Key Biodiversity Areas**

	Important Bird and Biodiversity Areas (IBAs); [BirdLife](http://datazone.birdlife.org/country/united-kingdom/ibas)

IBAs data was provided by Birdlife International. The data is compiled by Royal Society for Protection of Birds (RSPB) which is the UK Birdlife partner.

	Important Plant Areas (IPAs); [PlantLife](https://www.plantlife.org.uk/uk/nature-reserves-important-plant-areas/important-plant-areas)

	Alliance for Zero Extinction ([AZEs](https://zeroextinction.org/site-identification/2018-global-aze-map/)) sites. - None are located in UK


**2.	Protected Areas**

[World Database on Protected Areas (WDPA)](https://protectedplanet.net/country/GB).  These data were compared to data on protected areas from DEFRA. The data used to compare WDPA data was provided as an attachment by DEFRA. The datasets were similar in terms of names and number of protected areas and area covered. DEFRA confirmed that they provide updates on changes to any protected areas dataset to WDPA on a regular basis. 


WDPA data were chosen due to the inclusion of data on the date of designation of each protected area. Additionally, the WDPA data uses international designations of protected areas. This improves comparability with other countries. Only protected areas with 'Status' as 'Designated' were used in this analysis.


**3.	Ecosystem Type**

	The [Land Cover Map 2015](https://www.ceh.ac.uk/services/land-cover-map-2015) (LCM2015) from UK Centre for Ecology & Hydrology (UKCEH) is derived from satellite images and digital cartography and provides land cover information for the whole of the UK. The LCM2015 10 Aggregate Classes were used as ecosystem types for this analysis. The data set, which is based on the UK Biodiversity Action Plan Broad Habitat Classes, was chosen as the most appropriate geographic dataset for representing ecosystems for the whole of the UK. In the indicator metadata, there is no definition of ecosystem and what datasets to use.


**4.	Region boundaries**

Country and region boundaries were taken from [Open Geography portal](https://geoportal.statistics.gov.uk/):

	[England regions](https://geoportal.statistics.gov.uk/datasets/regions-december-2019-boundaries-en-bfe)  


	[country boundaries for Scotland, Wales and Northern Ireland](https://geoportal.statistics.gov.uk/datasets/countries-december-2019-boundaries-uk-bfe)

## Methodology

The analysis for this indicator was carried out in ArGIS PRO.


The indicator is calculated from data derived from a spatial overlap between a protected areas layer and a terrestrial and freshwater Key Biodiversity Areas layer (IBAs and IPAs). The value of the indicator at a given point in time (Status Year), is computed as the mean percentage of each Key Biodiversity Area currently recognised that is covered by protected areas.


For this analysis, the value of the indicator was determined at four-year steps from 1999 to 2019. The values for 1999 shows all KBAs covered by protected areas designated on or before 1999. The values for 2003 shows all KBAs covered by protected areas designated on or before 2003 including those before 1999. Yearly intervals could have been used, however a four-year interval was chosen because there are not large changes in protected area coverage on annual basis. It is also computationally expensive to calculate the indicator annually. The year 1999 was chosen as the starting point because there were minimal changes in protected area before 1999.



### Feature layers

The Key Biodiversity Areas (KBA) data was a merge of IBA and IPA datasets. There are no AZEs in the UK so no data from these were used. The IBA and IPA feature layers overlap in some areas. Therefore, to avoid double counting the area covered, the two layers were merged and dissolved to create one feature layer. Countries are expected to review and update KBAs every 8-12 years and the last and only assessment in the UK was in 2007. The KBA dataset do not include year of creation so there is only one layer used for this analysis throughout the whole time series.


The Protected Area (PA) layer includes the date on which each protected area was designated (‘Status_Year’). For each four-year step, all protected areas designated on or before the interval year using the 'Status_Year' were selected and separated in a GIS. As some PAs overlap in area, this selection was then merged and dissolved to create a single layer to avoid double counting the area. This layer contains the boundaries of all PAs that were designated on or before the interval year including the interval before. Thus, all PAs designated on or before 1999 are counted in 1999, and for 2003 all PAs up to 2003 are counted.


### Intersections

To determine the area of protected areas (PAs) by ecosystem type, the layer containing designated PAs for each window was intersected with the LCM15 Aggregate Class layer. 


The area covered by KBAs for each ecosystem type and for each UK region was determined by intersecting these three layers (KBAs, LCM15 Aggregate classes, and UK regions). None of these three layers currently have a time element (the boundaries are the same across the whole time series). 


To determine the area of KBAs covered by PAs, the KBA layer was intersected with the layer containing designated PAs for each four-year step.


Finally, the three resulting layers (area of PAs by ecosystem type, area of KBAs by ecosystem type and UK regions, and area of KBAs covered by PAs) were intersected. This could then be used to calculate the area of KBAs covered by PAs by region and ecosystem type. 


### Output statistics

Computational formula = **(ukRegions_LCM15_KBAinPA_Dissolve_StatusYear / KBA_LCM15_ukRegions) * 100**

The statistics from the computation were tabulated showing proportion of KBAs in protected areas by ecosystem type for the whole of the UK, its constituent countries, and regions in England for the years 1999, 2003, 2007, 2011, 2015 and 2019.

### Limitations

A key limitation of this indicator is that identification of Key Biodiversity Areas to date has focused mainly on specific subsets of biodiversity, for example birds (for IBAs) and highly threatened species (Alliance for Zero Extinction sites). There are limited geographic datasets of other levels of biodiversity and taxonomic groups. 


While this indicator is currently reported over four-year steps, it is possible to calculate it on a yearly basis. However, a four-year window was chosen to reduce the computational burden. The compromise was considered acceptable given that there were not large changes in protected area coverage on a yearly basis.


Whilst land cover shows change over time, and Land Cover Maps produced after 2015 have been created, LCM15 was used for the whole time series. This is because this was the most current map available at the time of analysis.


To distinguish coastal from freshwater and terrestrial ecosystems for this analysis, all areas outside of the Land Cover Map boundary were classified as coastal and were not considered in the analysis.  


Key Biodiversity Areas are currently fixed and do not show change over time, despite the case that important sites for biodiversity are likely to shift, for example, with changes in land use and climate change. In order to safeguard important sites and stem the decline in biodiversity, there is need therefore to measure and monitor changes in KBAs on a more frequent basis.


For some regions, current limitations on capacity and technology mean that it will take time to compile the necessary data and level of detail to demonstrate that sites meet the quantitative thresholds associated with the KBA criteria. 


It should be noted that areas not identified as KBAs are not necessarily of lesser importance. Future work could be done to include areas of national significance in addition to KBAs.







