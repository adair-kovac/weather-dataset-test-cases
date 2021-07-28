While nothing should change between the intermediate test cases and the archive being "done",
there are still some last things to wrap up. Additionally, make sure to make the test code and 
performance results publicly available!

## Suggested test cases
- The intermediate whole-use test cases, but publish them this time
- Check for significant missing data (e.g. missing model runs)
    - If it can't be backfilled from an existing archive, consider documenting it 
    - You could even provide code for a reasonable transformation on the dataset to fill in the missing data
- If the archive updates continuously with new model runs, test
    - creating a job that pulls the data as soon as it's available––document the latency relative to model initialization time
    - pulling several variables from the most recent model run as if to initialize another model