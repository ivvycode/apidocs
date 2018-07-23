# Dates

Responses from the iVvy API may contain dates. In all cases \(unless otherwise stated in documentation for the specific action\) the dates are in Universal Coordinated Time \(UTC\). Care must be taken when using or displaying these dates to ensure they: a\) maintain their UTC time zone for communication with the API, and; b\) represented in the appropriate time zone for users utilizing the date.

Dates may be represented as a string which must be parsed appropriately if it is to be used. Where possible any dates will be converted to the[ iVvy Timestamp Format](../development-reference/timestamp-format.md), which is a simple to understand text format to represent a specific point in time to the second.

