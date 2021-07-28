There are a number of different ways that data may be accessed. Think about which of these
you want to support or evaluate for performance and ease of use.

## Environment differences
- Local vs cloud
   - Local
        - opening the cloud data in code 
        - opening downloaded files stored on a local/network drive
   - Cloud
     - Same cloud, same region
     - Same cloud, different region (your data might not be the consumer's only source)
     - Different cloud
     - High vs low parallelization
    
## Who's accessing?
- Software
  - How many machines simultaneously?
- Human
  - Experienced with the dataset vs exploring it for the first time
  - Experienced with the tools (xarray, gcp/aws, etc) vs new to one or more
  - Someone who wants to do interactive data science vs a very specific computation
    
## Time considerations
- Near real-time access or analysis of past/static data?
- How much latency can they tolerate?

## Which dimensions are data being looked at across?
- Model init time, forecast lead time, actual time for multiple forecasts, geospatial domain,
ensemble members, etc
- For some datasets, it's fairly common for the initial hour of each model run to be
accessed much more frequently than the forecast hours. That should be considered in chunking.
- Note that one person's "dimension" might be another person's "a bunch of separate datasets". 
  If multiple datasets are being written, make sure they can be easily/efficiently combined into 
  one data structure for analysis.