# Collision Model Editing #

For users seeking to edit the collision models of built-in or new robots, this is a guide to creating a collision model of any complexity.

## Assigning a Model to a Robot ##

Robots in JBSim, as defined in the Robots file, can define their collision models using the "model" attribute. So, the generic CBC2 robot might have a line like:
```
cbc2.model = generic
```
This will tell JBSim to look at the _"models/generic.txt"_ file for collision model information.

## Inside a Collision Model ##

Each collision model is a plain text file. Try opening one of the built-in models, and you will see something like this:
```
# Collision model for Create

# How it works:
# ...

base = ellipse, -165, -165, 330, 330
base.0 = subtract, rect, -165, -165, 40, 330
```
This model declares a 330mm by 330mm ellipse (a circle with radius 165 mm), and removes a 40mm wide rectangular section from the back.

## Collision Model Details ##

  * Collision models have units of millimeters, and have the origin at the robot's center of turn.
  * A file can contain an arbitrary number of models.
  * A **model** is defined by one or more directives.
    * A **directive** is a line of the form `model.# = `_data_ where the numbers follow in increasing order starting from 0.
    * Each model begins with a directive that lacks a number which defines the base geometry for that model. This directive has no operation.
    * Each subsequent directive must have an **operation** which dictates how the shape referenced in that line will be used. The operation can be one of: **add**, **subtract**, **intersect**, or **xor**.
    * The data in a directive is a sequence of comma separated values.
    * All directives must continue with a shape declaration and optional parameters. Allowable shapes are **ellipse**, **rect** angle, and **poly** gon. Another model in the file can be referenced by name as well.
    * If the shape is **ellipse** or **rect**, four parameters must be provided: the x and y coordinates of the upper left, and the width and height of the shape.
    * If the shape is **poly**, an even number of parameters representing x and y coordinates of points must be provided. The polygon will be closed automatically.
    * Directives are applied in numerical order, _not_ the order in the file.
  * The **base** model is the model that will define your robot. In many cases, it is the only model that need be defined.
  * A model cannot have a name that matches a primitive shape.
  * There is _no_ "negative area": making a model which subtracts something from empty area will leave the empty area unchanged, and including this model as a part of another will not subsequently erase the subtracted area from the main model.
  * All items in model files are _case sensitive_.

## Example Models ##

```
# A hollow, square box with side length 200mm and hole size 100mm

base = rect, -100, -100, 200, 200
base.0 = subtract, rect, -50, -50, 100, 100
```

Equivalently:
```
# A hollow, square box with side length 200mm and hole size 100mm
#  This representation uses a sub-model

hole = rect, -50, -50, 100, 100

base = rect, -100, -100, 200, 200
base.0 = subtract, hole
```