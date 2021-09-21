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

	Important Bird and Biodiversity Areas (IBAs); BirdLife

	Important Plant Areas (IPAs); PlantLife

	Alliance for Zero Extinction (AZEs) sites. - None are located in UK

## Data

1.	KBAs – Key Biodiversity Areas – (Important Sites for Terrestrial and Freshwater Biodiversity)

	Important Bird and Biodiversity Areas (IBAs); [BirdLife](http://datazone.birdlife.org/country/united-kingdom/ibas)

	Important Plant Areas (IPAs); [PlantLife](https://www.plantlife.org.uk/uk/nature-reserves-important-plant-areas/important-plant-areas)

	Alliance for Zero Extinction ([AZEs](https://zeroextinction.org/site-identification/2018-global-aze-map/)) sites. - None are located in UK
	
2.	Protected Areas (PAs)
	World Database on Protected Areas (WDPA) https://protectedplanet.net/country/GB (QA’d using data on protected areas from JNCC-DEFRA. WDPA data was preferred as it has attribution that includes “Status_Year” which is the date of designation of each protected area. Also the WDPA data uses international designations of the protected areas which makes stats for the indicator comparable to other countries and makes the methodology for the indicator applicable to other countries or regionally/globally.

3.	Ecosystem Type (LCM15_BroadHabitat)
	Land Cover Map 2015 (LCM2015) from UK Centre for Ecology & Hydrology (UKCEH) https://www.ceh.ac.uk/services/land-cover-map-2015
	
4.	Regions - ukRegions
	England regions from Open Geography portal https://geoportal.statistics.gov.uk/datasets/regions-december-2019-boundaries-en-bfe combined with 
	country boundaries for Scotland, Wales and Northern Ireland https://geoportal.statistics.gov.uk/datasets/countries-december-2019-boundaries-uk-bfe

5.	Define Computational formula for Indicator according to UN metadata
This indicator is calculated from data derived from a spatial overlap between protected areas layer and terrestrial and freshwater Key Biodiversity Areas layer (including Important Bird and Biodiversity Areas, Alliance for Zero Extinction sites, and other Key Biodiversity Areas). 
The value of the indicator at a given point in time, based on data on the year of protected area establishment recorded, is computed as the mean percentage of each Key Biodiversity Area currently recognised that is covered by protected areas.

Computational formula = (ISTFB area / PA area (Designation year)/Ecosystem Type * 100


