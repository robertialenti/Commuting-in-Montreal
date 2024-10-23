# Commuting in Montreal
This project visualizes commuter modal shares by census tract in the Montreal Census Metropolitain Area (CMA). Specifically, it plots the share of 2021 Census-takers, in each Census tract, commuting to work by personal vehicle, with public transit, or by active transportation, respectively. While commuting patterns reported in 2021 were likely affected by the COVID-19 pandemic, the visualization remains a good indication of how residents in various parts of the city commute to work.

## Data
Data is gathered from Statistics Canada's [Table 98-10-0480-01](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=9810048001). The data is collected using the stats_can API for Python. The Census boundary lines - that is, the boundaries of each census tract - are made available by [Statistics Canada](https://www12.statcan.gc.ca/census-recensement/2021/geo/sip-pis/boundary-limites/index2021-eng.cfm?year=21). Data is uploaded using GitHub's Large File Storage (LFS) for others' convenience.

## Code
Python code is written in a Jupyter notebook. I first read in the commuting data and merge in boundary lines. I focus only on the Montreal CMA. I also consider only aggregate modal types. For instance, I retain "Active Commuting", but remove its constituent modal types, including "Bicycle" and "Walking". Next, I express the number of people commuting in each census tract - by modal type - as a share of the total number of commuters. 

Once the data is processed, I begin preparing it for spatial analysis. I reproject the Lambert conformal conic map projection, widely used by Statistics Canada, to standard lat/long coordinates. For each Census tract, I calculate the polygon's centroid. I then calculate the mean of all centroid latitude and longitude values, which I use to center the map. Census tracts without commuters are greyed out.

## Results
I plot the shares for three modal types: (i) car, truck, or van, (ii) public transit, and (iii) active transportation. As expected, people located in suburban regions of the Montreal CMA, where alternative transportation options may be limited, predominantly commute with a personal vehicle. Use of public transit is highly correlated with distance to the metro. For instance, it is clear to see a higher public transit modal share in corridors along the Green and Orange lines of Montreal's metro. Census tracts with a high active transportation modal share are concentrated in the relatively central Plateau Mont-Royal borough, where bicycle infrastructure is the most comprehensive.

<img src="https://github.com/robertialenti/Commuting-in-Montreal/raw/main/figures/Car, truck or van_map.jpg">

<img src="https://github.com/robertialenti/Commuting-in-Montreal/raw/main/figures/Public transit_map.jpg">

<img src="https://github.com/robertialenti/Commuting-in-Montreal/raw/main/figures/Active transportation_map.jpg">
