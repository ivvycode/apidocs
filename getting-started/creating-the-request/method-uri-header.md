# Method/URI Header

This is a line consisting of the method of the request, followed by the request URI, followed by the HTTP version. i.e.

`POST /api/1.0/event?action=getEventList HTTP/1.0`

This example is for a request, to iVvy’s api ‘event’ namespace, calling the ‘getEventList’ API call, using HTTP version 1.0. Note the HTTP method for calls to the iVvy API are all POST requests. The api version being called is 1.0. Currently supported versions are:

* 1.0

The URI in the request must always start with /api/{version} \(where {version} is the specific api version, e.g. 1.0\) followed by the namespace of the eventual api call to make. All requests must also provide the action parameter indicating the API call to invoke.

