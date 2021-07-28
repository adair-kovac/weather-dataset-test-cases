To save time and money in development, test cases should be run over the 
first available prototype of the data.

Currently, that's assumed to be:
- One model run of data
- A potentially limited number of available data variables
- The full geospatial grid and potentially the full forecast time grid

## Suggested test cases

- Simple data retrieval:
    - Space variations:
        - Data at a single gridpoint
        - Data within a latitude/longitude region
        - Data for the whole grid
    - Number of variable variations:
        - Metadata listing all variables without triggering any data download
        - One variable accessed at a time
        - Two variables accessed at a time
        - All variables opened in one dataset
    - Forecast time variations (if applicable):
       - Only the initial conditions
       - The entire forecast
       - Random access to a specific forecast hour
    - Merge of any separate datasets being written
    
- Whole data use cases:
    - Calculate the spatial average of a variable at the initial time
    - Plot a time series of a forecast variable at a gridpoint
    - Plot a (time-averaged) variable on a map (this involves testing how easy it is to deal with the coordinate projection)
    
- Error test cases:
    - Create input datasets with missing and invalid data and make sure the data conversion code handles them
    - See how the data retrieval/use cases work over missing data 
    