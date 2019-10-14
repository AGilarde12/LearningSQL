# Denormalized Data

Combine columns from multiple tables in a single table - Pre-joining 

* Joining done once
* Useful when data is queried multiple times
* If query response time is more important you should denormalize

Data source --> Time Series Data + Related Data --> Pre-Joined data <-- Query this table

Just remember this usses more data storage 
and the Ingest process is more complex
