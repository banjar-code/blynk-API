# blynk-API

<h1>Control 8 relays using esp8266 and blynk API</h1>

In this simple project using html, css, and ajax

https://docs.blynk.io/en/blynk.cloud/https-api-overview

<h2>Get Multiple Datastream values</h2>

In some cases it's important to get the datastream values with one call. This endpoint allows you to get the stored values of the multiple Datastreams. 
Returned type depends on the datastream type. 

Example:
https://blynk.cloud/external/api/get?token=Rps15JICmtRVbFyS_95houlLbm6xIQ2L&v1&v2&v3&v4&v5&v6&v7&v8

Parameters   
Path
pin                              string           Virtual pin number (should start with "v")
token                            string           Device auth token

Responses
200                              Value successfully retrieved.
400                              Could not find a device token or Wrong pin format

<h2>Update the Datastream value</h2>
This endpoint allows you to update the value of the Datastream value via GET request.

Example:
https://blynk.cloud/external/api/update?token=ffujYGgbf805tgsf&v1=1

Parameters
Path
value                           string            The desired value of the Datastream. Will be parsed based on the Datastream data type (int, double, string) and bounded with min / max values of datastream settings. In case value doesn't match the Datastream type error will be returned.
pin                             string            Virtual pin number (should start with "v")
token                           string            Device auth token

Responses
200                             Success
400                             'Could not find a device token' or 'Wrong pin format' or 'Value doesn't match the Datastream data type' or 'No datastream setup for that pin'
