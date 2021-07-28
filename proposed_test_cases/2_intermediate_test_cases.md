Once a single model run of data has proven successful, further tests will be needed first to make sure data
from different model runs can be accessed together, then to check the performance on a largish subset of data before
creating the complete archive.

It's recommended to run these tests:
- As soon as 2 model runs are available
- After O(10) model runs are available (e.g. 1 day of an hourly model)
- After O(100) and O(1000) model runs are available (4 days and 1 month respectively 
  for an hourly model)

## Suggested test cases

- Simple data retrieval
    - The prototype test cases, but against 
        - a random-access model run time
        - all available run times, as a datacube
    - Time series of initial data
    - All forecast values for a given time at a given gridpoint
    - Run at least one of these tests against every available data variable
- Whole use test cases
    - Plot forecasts for the same hour range but from different initial times
    - Compare forecast values to values from later model runs' initial state
    - Compute climatologies (e.g. max/min, 50th, and 95th percentiles of a variable)
       - at a gridpoint (running from a laptop)
       - across the entire domain (using distributed computing on the cloud)
    - Compare at least one of these analyses to an equivalent analysis on data from
        - a completely different model
        - the source data, e.g. the grib2 or netCDF4 files that are being converted for better cloud access
- Error tests
    - Test timeseries and datacube retrieval when data is missing/invalid at some gridpoints at some times
    - Run data retrieval and use test cases when certain hours are missing
    - Error tests don't need to be run over more than 3 hours