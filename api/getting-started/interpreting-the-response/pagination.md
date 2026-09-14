# Pagination

Some requests \(mostly the requests that return [collections](collections.md)\) may also accept some pagination options.

* perPage: The number of items to return per page. Note that most requests have a cap on this number and providing a perPage option greater than that cap will not have any effect.
* start: The record to start paging from. Note this number is zero based, i.e. to return results from the very first result, the start will need to equal 0 \(which is the default\). Note also this is not the page to start at. For example to get the second page from a list of results that have 20 results per page, the start property will need to equal 20 \(i.e. starting at the 21st result\)

