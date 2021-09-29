# **Goal 15**: Protect, restore and promote sustainable use of terrestrial ecosystems, sustainably manage forests, combat desertification, and halt and reverse land degradation and halt biodiversity loss.

## **Target 15.1**: By 2020, ensure the conservation, restoration and sustainable use of terrestrial and inland freshwater ecosystems and their services, in particular forests, wetlands, mountains and drylands, in line with obligations under international agreements

### **Indicator 15.1.2**: Proportion of important sites for terrestrial and freshwater biodiversity that are covered by protected areas, by ecosystem type.

### Definition:
The indicator Proportion of important sites for terrestrial and freshwater biodiversity that are covered by protected areas, by ecosystem type shows temporal trends in the mean percentage of each important site for terrestrial and freshwater biodiversity (i.e., those that contribute significantly to the global persistence of biodiversity) that is covered by designated protected areas and Other Effective Area-based Conservation Measures (OECMs).

### Concepts:

#### Protected Areas
Protected areas, as defined by the International Union for Conservation of Nature (IUCN; Dudley 2008), are clearly defined geographical spaces, recognized, dedicated and managed, through legal or other effective means, to achieve the long-term conservation of nature with associated ecosystem services and cultural values.

The status **"designated"** is attributed to a protected area when the corresponding authority, according to national legislation or common practice (e.g., by means of an executive decree or the like), officially endorses a document of designation. 

#### Key Biodiversity Areas (KBAs)

KBAs or Important Sites for Terrestrial and Freshwater Biodiversity are sites contributing significantly to the global persistence of biodiversity. KBAs are identified following global criteria set out in A Global Standard for the Identification of Key Biodiversity Areas (KBAs) (IUCN 2016) applied at national levels. KBAs encompass:

	Important Bird and Biodiversity Areas (IBAs); Royal Society forProtection of Birds which is the BirdLife Partner for the UK

	Important Plant Areas (IPAs); PlantLife

	Alliance for Zero Extinction (AZEs) sites. - None are located in UK

## Data

**1.	Key Biodiversity Areas**

	Important Bird and Biodiversity Areas (IBAs); [BirdLife](http://datazone.birdlife.org/country/united-kingdom/ibas)

IBAs data was provided by Birdlife International. The data is compiled by Royal Society for Protection of Birds (RSPB) which is the UK Birdlife partner.

	Important Plant Areas (IPAs); [PlantLife](https://www.plantlife.org.uk/uk/nature-reserves-important-plant-areas/important-plant-areas)

	Alliance for Zero Extinction ([AZEs](https://zeroextinction.org/site-identification/2018-global-aze-map/)) sites. - None are located in UK

** Regarding important sites, the biggest limitation is that site identification to date has focused mainly on specific subsets of biodiversity, for example birds (for Important Bird and Biodiversity Areas) and highly threatened species (for Alliance for Zero Extinction sites). There is limited geographic datasets of other different levels of biodiversity and taxonomic groups. This analysis uses the available datasets for the UK, which are IBAs and IPAs.

**2.	Protected Areas**

[World Database on Protected Areas (WDPA)](https://protectedplanet.net/country/GB)  (QA’d using data on protected areas from JNCC-DEFRA. WDPA data was preferred as it has attribution that includes “Status_Year” which is the date of designation of each protected area. Also the WDPA data uses international designations of the protected areas which makes stats for the indicator comparable to other countries and makes the methodology for the indicator applicable to other countries or regionally/globally. Only protected areas with 'Status' as 'Designated' were used in this analysis.

**3.	Ecosystem Type (LCM15_AggregateClass)**

	[Land Cover Map 2015](https://www.ceh.ac.uk/services/land-cover-map-2015) (LCM2015) from UK Centre for Ecology & Hydrology (UKCEH) 
The LCM2015 10 Aggregate Classes were used as ecosystem types for this analysis. 
The data set was chosen a the most appropriate geographic dataset for representing ecosystems for the whole of the UK. in the indicator metadata, there is no definition of ecosystem and what datasets to use. ** In the future iterations of the indicator, there maybe an opportunity to use different ecosystem type datasets if more appropriate.

**4.	Region boundaries (ukRegions)**

	[England regions](https://geoportal.statistics.gov.uk/datasets/regions-december-2019-boundaries-en-bfe) from Open Geography portal  combined with 
	[country boundaries for Scotland, Wales and Northern Ireland](https://geoportal.statistics.gov.uk/datasets/countries-december-2019-boundaries-uk-bfe)

## Methodology


This indicator is calculated from data derived from a spatial overlap between protected areas layer and terrestrial and freshwater Key Biodiversity Areas layer (including Important Bird and Biodiversity Areas, Alliance for Zero Extinction sites, and other Key Biodiversity Areas). 
The value of the indicator at a given point in time, based on data on the year of protected area establishment recorded, is computed as the mean percentage of each Key Biodiversity Area currently recognised that is covered by protected areas.

The analysis for this indicator was carried out in ArGIS PRO.


### Feature layers

The ISTFB or Key Biodiversity Areas (KBAs) data was a merge of IBAs and IPAs data. There is no AZEs in UK so no data from these was used. The IBAs and IPAs feature layers overlap in some areas so to avoid double-counting area covered, the 2 were merged and dissolved to create one feature layer. The IBAs and IPAs datasets do not include Year of creation so there is only one layer used for this analysis.

The PA layer has 'Status_Year' which was used to determine area protected at each point in time. For this analysis, the value of the indicator was determined at 4 year intervals from 1999 to 2019. This 4-year interval was arbitrary and this indicator could be analysed at yearly intervals. Also, 1999 was used as the starting point beause there is minimal changes in protected area before 1999.

For each interval, a selection criteria was used to separate all protected areas designated on or before the 'Status_Year'. This selection was then merged and dissolved to create a single layer 'PA_Dissolve_StatusYear'. This was to avoid double counting the area.

### Intersection

'PA_Dissolve_StatusYear' intersect with 'LCM15_AggregateClass' created 'LCM15_PA_Dissolve_StatusYear'. This layer was used to determine area of protected areas by ecosystem type.

'KBA' intersect with 'LCM15_AggregateClass' and 'ukRegions' created 'KBA_LCM15_ukRegions'. This layer was shows area covered by KBAs by ecosystem for each UK region.

'KBA' layer intersected with 'PA_Dissolve_StatusYear' layer for each interval to create 'KBAinPA_Dissolve_StatusYear' layer. This was to determine area of KBAs covered by PAs.

'KBAinPA_Dissolve_StatusYear' was intersected with 'LCM15_PA_Dissolve_StatusYear' and 'ukRegions' to create 'ukRegions_LCM15_KBAinPA_Dissolve_StatusYear' layer. This layer shows KBA in protected areas by region by ecosystem type.


### Output statistics

Computational formula = **(ukRegions_LCM15_KBAinPA_Dissolve_StatusYear / KBA_LCM15_ukRegions) * 100**

The statistics from the computation were tabulated showing proportion of KBAs in protected areas by ecosystem type for the whole of the UK, 4 countries and regions in England for the years 1999, 2003, 2007, 2011, 2015 and 2019.




