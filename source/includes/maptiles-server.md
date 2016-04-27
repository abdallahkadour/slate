# API-Description

## /mts

### GET
Request to get the meta information of a map by mapId.

#### HTTP Request

GET `principals/:principalId/maps/:mapId` 

#### URL Parameters
Parameter| Description
---------| ------------
principalId| The id of the Principal.
mapId    | The id of the map in the database.


#### Responses

Code | Description | message
-------| ---------------- | -----------
200  | Map was found | The name and description of the map.|
404  | There is no map found in the database  |-|.
400| Missing required attribute.
500  | An internal error occurred| - |.
 
### Post 
Create a new map.

#### HTTP Request

POST `principals/:principalId/mapid/:mapId`

#### URL Parameters

Parameter| Description
--------- |------------
principalId| The id of the Principal.
mapId    | The id of the map in the database.

#### Query Parameters

Parameter| Description
--------- |------------
name      | The name of the new map.
mapId      | The id of the new map.

#### Headers

Parameter | Wert
--------- | -----------
Accept | application/json; charset=UTF-8
Content-Type | application/json; charset=UTF-8

#### Responses

Code | Description
---- | ---------
201  | The new map has been successfully created.
409  | Conflict.
400  | Missing required attribute.
500  | An internal error is occured.

### PUT

Request to update a map.

#### HTTP Request

PUT `principals/:principalId/mapid/:mapId/`

#### URL Parameters

Parameter| Description
---------| ------------| 

principalId| The id of the Principal.
mapId    | The id of the map in the database.

#### Query Parameters

Parameter| Description|
--------- |------------
newName   | The name of the new map.
NewDescription | The id of the new map.

#### Headers

Parameter | Wert
--------- | -----------
Accept | application/json; charset=UTF-8
Content-Type | application/json; charset=UTF-8

#### Responses

Code | Description
---- | ---------
204  | The map has been successfully updated.
400  | Map not found.
400  | Missing required attribute.
500  | An internal error is occurred.

### DELETE

Delete a map. On this request the map and the tiles of it would be deleted.

#### HTTP Request

DELETE `principals/:principalId/mapid/:mapId/`

#### URL Parameters

Parameter| Description
--------- |------------
principalId| The id of the Principal.
mapId    | The id of the map in the database.

#### Responses

Code | Description
---- | ---------
204  | The map has been successfully deleted.
400  | Missing required attribute.
500  | An internal error is occurred.
