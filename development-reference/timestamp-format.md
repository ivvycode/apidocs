# Timestamp Format

The iVvy API uses a timestamp format to represent dates and times. Every date used in the API is in UTC. It is up to the consumer of the API to convert the time to the correct timezone of the final recipient of the data. The format is a simple text-based format in the following form:

`yyyy-mm-dd HH:mm:ss (UTC)`

**Where:**

* 'yyyy' is the 4 digit year of the date,
* 'mm' is the two digit month of the date, where January = 01 and December = 12
* 'dd' is the two digit day of the month,
* 'HH' is the two digit hour,
* 'mm' is the two digit minute, and
* 'ss' is the two digit second
* \(UTC\) is optional text at the end

**Examples:**

* 2020-11-24 15:33:46
* 2021-05-13 07:05:33 UTC
* 2019-01-01 21:47:04

