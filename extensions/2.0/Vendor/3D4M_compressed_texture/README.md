# 3D4M_compressed_texture

**Note**: Name, subject to change.

## Contributors

* Volodymyr Boichentsov, 3D4Medical, LLC

## Status

Draft/Proposal

## Dependencies

Written against the glTF 2.0 spec.

## Overview

This extension defines a schema to use different compressed textures in glTF format. This allows glTF to support compressed textures. Idea is that no need to spend time on unpacking from dds, ktx, pvr, etc containers.

Ideal use case for this extension is when client request gltf file with specific compression type from hosted application on remote server.

## glTF Schema Updates

If a `texture` contains an `extension` property and the `extension` property defines its `3D4M_compressed_texture` property, then `compression` property can be used to test against supported formats.

If the fallback source image is not provided, then `3D4M_compressed_texture` must be added to `extensionsRequired`.

```javascript
"extensionsRequired" : [
    "3D4M_compressed_texture"
]

```

Usage of the extension must be listed in the `extensionsUsed`. 

```javascript
"extensionsUsed" : [
    "3D4M_compressed_texture"
]

```

Below is an example of what a part of a glTF file may look like if  extension is set:

```javascript

"textures": [
    {
        "source": 0,
        "sampler": 0,
        "extensions": {
            "3D4M_compressed_texture": {
                "width" : 1024,
                "height" :  1024,
                "target" : 3553,
                "sources" : [ 10, 11, 12, 13, 14, 15 ],
                "compression" : 33776
            }
        }
    }
]

```
#### width
The `width` property defines the width size of texture for level 0.

#### height
The `height` property defines the width size of texture for level 0.

#### target
Specifies the target to which the texture is bound. Used as first argument for [`glCompressedTexImage2D`](https://www.khronos.org/registry/OpenGL-Refpages/es2.0/xhtml/glCompressedTexImage2D.xml) or [`glCompressedTexImage3D`](https://www.khronos.org/registry/OpenGL-Refpages/es3/html/glCompressedTexImage3D.xhtml), etc. 

#### sources
Indices on bufferView's which used for each level of texture. First source representing level 0, second is level 1 and so on. Each next source is must be previous size divide by 2. For example 0 level is 1024, next is 512 and next 256, etc.
Second argument of [`glCompressedTexImage2D`](https://www.khronos.org/registry/OpenGL-Refpages/es2.0/xhtml/glCompressedTexImage2D.xml) or [`glCompressedTexImage3D`](https://www.khronos.org/registry/OpenGL-Refpages/es3/html/glCompressedTexImage3D.xhtml).

#### compression
Known as `internalformat`, third argument, for [`glCompressedTexImage2D`](https://www.khronos.org/registry/OpenGL-Refpages/es2.0/xhtml/glCompressedTexImage2D.xml) or [`glCompressedTexImage3D`](https://www.khronos.org/registry/OpenGL-Refpages/es3/html/glCompressedTexImage3D.xhtml). 

## Example 
```c
...
glCompressedTexImage2D(target, 0, compression, width, height, 0, dataSources[0].length, dataSources[0].bytes);
```


## JSON Schema

For full details on the `3D4M_compressed_texture` extension properties, see the [schema](schema/3D4M_compressed_texture.schema.json).


