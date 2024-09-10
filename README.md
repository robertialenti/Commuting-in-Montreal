# Commuting in Montreal
This project visualizes commuter modal shares by census tract in the Montreal Census Metropolitain Area (CMA). Specifically, it plots the share of 2021 Census-takers, in each Census tract, commuting to work by personal vehicle, with public transit, or by active transportation, respectively. While commuting patterns reported in 2021 were likely affected by the COVID-19 pandemic, the visualization remains a good indication of how residents in various parts of the city commute to work.

## Data
Data is gathered from Statistics Canada's [Table 98-10-0480-01](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=9810048001). The Census boundary lines - that is, data outlining the boundaries of each census tract - are made available by [Statistics Canada](https://www12.statcan.gc.ca/census-recensement/2021/geo/sip-pis/boundary-limites/index2021-eng.cfm?year=21). Data is uploaded using GitHub's Large File Storage (LFS).

## Code
Python code is written in a Jupyer notebook. I first read in the commuting data and merge in boundary lines. I focus only on the Montreal CMA. I consider only aggregate modal types. For instance, I focus on "Active Commuting", rather than "Bicycle" and "Walking", separately. Next, I express the number of people commuting by modal type as a share of the total number of commuters.

## Results
I plot the shares for three modal types: (i) car, truck, or van, (ii) public transit, and (iii) active transportation. Census tracts without population are greyed out. As expected, suburban regions of the CMA ____. Use of public transit is highly correlated with distance to the metro. Census tracts with a high active transportation modal share are concentrated in the Plateau Mont-Royal borough.

<img src="https://github.com/robertialenti/Commuting-in-Montreal/raw/main/figures/Car, truck or van_map.jpg">

<img src="https://github.com/robertialenti/Commuting-in-Montreal/raw/main/figures/Public transit_map.jpg">

<img src="https://github.com/robertialenti/Commuting-in-Montreal/raw/main/figures/Active transportation_map.jpg">
