Potential problems:

* Times may have different precision

* More precise, less likely to match

* Clock Skew - (use network time services and minimize the risk of clock skew)

How to deal with them?

* Truncate time
** Drop most precise time elements
** use send or minute for example


Use a GROUP BY time
Choose a degree of precision
Use aggregate functions
Produce one row per time period

Just remember there may be some loss of precision and detail
