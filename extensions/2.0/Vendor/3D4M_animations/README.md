## Objects
* [`Animation Extension`](#reference-animation.schema-json) (root object)
   * [`Animation Controller`](#reference-animation.controller.schema-json)
   * [`Animation Joint`](#reference-animation.joint.schema-json)
   * [`Morph Controller`](#reference-animation.morph_controller.schema-json)

---------------------------------------
<a name="reference-animation.schema-json"></a>
### Animation

Animation container.

**Properties**

|   |Type|Description|Required|
|---|----|-----------|--------|
|**target**|`string`|Link to the geometry animated by the Controller. id of Geometry. (consider to deprecate and use index position)| :white_check_mark: Yes|
|**id**|`string`|Identifier of the Controller.| :white_check_mark: Yes|
|**jointsCount**|`integer`|Number of joints that effect by the Controller|No, default: `0`|
|**jointsIndices**|`string`|Indices of effecting joints. Saved as data base64.|No|

Additional properties are allowed.

#### animation_controller.json.target :white_check_mark: 

Link to the geometry animated by the Controller. id of Geometry. (consider to deprecate and use index position)

* **Type**: `string`
* **Required**: Yes

#### animation_controller.json.id :white_check_mark: 

Identifier of the Controller.

* **Type**: `string`
* **Required**: Yes

#### animation_controller.json.jointsCount

Number of joints that effect by the Controller

* **Type**: `integer`
* **Required**: No, default: `0`

#### animation_controller.json.jointsIndices

Indices of effecting joints. Saved as data base64.

* **Type**: `string`
* **Required**: No



---------------------------------------
<a name="reference-animation.joint.schema-json"></a>
### Animation Joint

Animation Joint container.

**Properties**

|   |Type|Description|Required|
|---|----|-----------|--------|
|**name**|`string`|Name of the Joint|No|
|**id**|`string`|Identifier of the Joint.| :white_check_mark: Yes|
|**index**|`integer`|Number joint position in the joints array| :white_check_mark: Yes|
|**count**|`integer`|Number of global transform matrices| :white_check_mark: Yes|
|**matrices**|`string`|Data with the Joint global transform matrices.| :white_check_mark: Yes|

Additional properties are allowed.

#### animation_joint.json.name

Name of the Joint

* **Type**: `string`
* **Required**: No

#### animation_joint.json.id :white_check_mark: 

Identifier of the Joint.

* **Type**: `string`
* **Required**: Yes

#### animation_joint.json.index :white_check_mark: 

Number joint position in the joints array

* **Type**: `integer`
* **Required**: Yes

#### animation_joint.json.count :white_check_mark: 

Number of global transform matrices

* **Type**: `integer`
* **Required**: Yes

#### animation_joint.json.matrices :white_check_mark: 

Data with the Joint global transform matrices.

* **Type**: `string`
* **Required**: Yes



---------------------------------------
<a name="reference-animation.morph_controller.schema-json"></a>
### Morph Controller

Animation Morph Controller container.

**Properties**

|   |Type|Description|Required|
|---|----|-----------|--------|
|**id**|`string`|Identifier of the Morph Controller.|No|
|**matricesCount**|`integer`|Number of original morph progress matrices|No, default: `0`|
|**matrices**|`string`|Original morph progress matrices|No|
|**targetsCount**|`integer`|Amount of morph targets in morph controllers.|No, default: `0`|

Additional properties are allowed.

#### morph_controller.json.id

Identifier of the Morph Controller.

* **Type**: `string`
* **Required**: No

#### morph_controller.json.matricesCount

Number of original morph progress matrices

* **Type**: `integer`
* **Required**: No, default: `0`

#### morph_controller.json.matrices

Original morph progress matrices

* **Type**: `string`
* **Required**: No

#### morph_controller.json.targetsCount

Amount of morph targets in morph controllers.

* **Type**: `integer`
* **Required**: No, default: `0`



---------------------------------------
<a name="reference-glTF.animation.schema-json"></a>
### Animation

Animation container.

**Properties**

|   |Type|Description|Required|
|---|----|-----------|--------|
|**name**|`string`|Name of the Animation|No|
|**id**|`string`|Identifier of the Animation.| :white_check_mark: Yes|
|**start**|`integer`|Number of start frame|No|
|**end**|`integer`|Number of end frame|No|
|**joints**|`animation.joint.schema.json` `[]`|List of all joints of the Animation.|No|
|**controllers**|`animation.controller.schema.json` `[]`|List of all controllers of the Animation.|No|
|**morphControllers**|`animation.morph_controller.schema.json` `[]`|Morph animation controllers with data to animate the model.|No|

Additional properties are allowed.

#### animation.json.name

Name of the Animation

* **Type**: `string`
* **Required**: No

#### animation.json.id :white_check_mark: 

Identifier of the Animation.

* **Type**: `string`
* **Required**: Yes

#### animation.json.start

Number of start frame

* **Type**: `integer`
* **Required**: No

#### animation.json.end

Number of end frame

* **Type**: `integer`
* **Required**: No

#### animation.json.joints

List of all joints of the Animation.

* **Type**: `animation.joint.schema.json` `[]`
* **Required**: No

#### animation.json.controllers

List of all controllers of the Animation.

* **Type**: `animation.controller.schema` `[]`
* **Required**: No

#### animation.morphControllers

Morph animation controllers with data to animate the model.

* **Type**: `animation.morph_controller.schema.json` `[]`
* **Required**: No

