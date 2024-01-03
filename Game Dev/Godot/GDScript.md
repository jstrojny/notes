A scripting language built into Godot. Similar to Python: dynamically typed and uses spacing for locality. Scripts inherit from whatever node they're attached to so a script on a Sprite2D has access to that, plus Node2D, plus CanvasItem. GDScript uses the `extends` keyword to denote inheritance.

## Keywords
### extends
Shows what a script inherits from. If left empty the script/object automatically inherits from refCounted so the engine can do memory management.

## Functions
Functions that started with an underscore are "virtual" functions. They are provided by the engine to be overridden.
## \_init()
Called anytime the object is created in memory.

## \_process(delta)
Available in any class that inherits from `node`. Called on every frame and takes a time delta argument representing the time elapsed since the previous frame.