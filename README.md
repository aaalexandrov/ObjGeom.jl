# ObjGeom

[![Build Status](https://travis-ci.org/aaalexandrov/ObjGeom.jl.svg?branch=master)](https://travis-ci.org/aaalexandrov/ObjGeom.jl)

[![Coverage Status](https://coveralls.io/repos/aaalexandrov/ObjGeom.jl/badge.svg?branch=master&service=github)](https://coveralls.io/github/aaalexandrov/ObjGeom.jl?branch=master)

[![codecov.io](http://codecov.io/github/aaalexandrov/ObjGeom.jl/coverage.svg?branch=master)](http://codecov.io/github/aaalexandrov/ObjGeom.jl?branch=master)

Planar geometric object generation / loading from .obj files

##Usage:

```
import ObjGeom

# to load a file
model = ObjGeom.load_obj("example.obj")

# to convert to GPU buffer friendly SOA format / 0-based indexed triangle list
vertexStreams, indices = ObjGeom.get_indexed(model)
# now vertex data arrays can be found in vertexStreams[:position], vertexStreams[:texCoord], vertexStreams[:normal]

# to generate a cube
cube = ObjGeom.prism(4)

# or a 10-sided pyramid shaded as a cone
cone = ObjGeom.pyramid(10, smooth = ObjGeom.SmoothSides)

# a smooth shaded sphere
ball = ObjGeom.sphere(20)

# to add texture coordinates by projecting along a direction
ObjGeom.add_texcoord(ball, [1f0, 0.5f0, -1f0])
```
