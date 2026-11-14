# Optimizing Electric Vehicle Charging Station Placement

Language: Python

This project integrates street network topology and American Community Survey (ACS) demographic data to determine mathematically optimal deployment sites for electric vehicle charging infrastructure in Austin, Travis County, Texas. 

## Questions to Answer

1. With a limited budget, where should a constrained set of charging stations be deployed across Travis County, Texas to minimize the overall demographic-demand-weighted travel distance?
2. How do composite demographic factors, specifically population density, road betweenness centrality, and median household income, shift optimal facility placement compared to traditional single-metric (i.e. population only) models?

## Data Sources

- OpenStreetMap via OSMnx and NetworkX
- U.S. Census Bureau data via TIGER/Line Shapefiles via pygris
- American Community Survey (ACS 5-year estimates) via pygris

## Methods

- Betweenness Centrality using OSMnx and NetworkX
- Point-in-Polygon spatial joins to map road intersections to census tracts
- P-Median Facility Location Problem formulated as a Mixed-Integer Linear Program (MILP)
  -   Created composite demand weight by combining population (40%), node centrality (40%), and median household income (20%) to determine optimal placement of Electric Vehicle (EV) charging stations
  -   Euclidean distance provided a higher average circuity ratio than typical U.S. Metropolitan benchmarks of 1.20-1.45
  -   Moved to True Network Distances (true network shortest path calculations) resulted in a circuity ratio of 1.388, within typical range
