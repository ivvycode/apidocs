# Timestamp Format

The iVvy API uses a timestamp format to represent dates and times. Every date used in the API is in UTC. It is up to the consumer of the API to convert the time to the correct timezone of the final recipient of the data. The format is a simple text-based format in the following form:

`yyyy-mm-dd HH:mm:ss`

Where

\| --- \| --- \| \| yyyy \| The 4 digit year of the date \| \| mm \| The two digit month of the date, where January = 01 and December = 12 \| \| dd \| The two digit day of the month \| \| HH \| The two digit hour \| \| mm \| The two digit minute \| \| ss \| The two digit second \|

