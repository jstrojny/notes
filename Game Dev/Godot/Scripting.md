Godot supports scripting for more complex behaviors. For instance, a camera node does not have screen shake built in and this behavior would need to be added by script.

Godot supports four languages for scripting:
1. [[GDScript]]
2. C#
3. C++
4. C

## GDScript
The assumed scripting language of choice. Built to be easy to use and tightly integrated with Godot. Object oriented and imperative.

## C\#
C# is officially supported as well. Because most scripts functions call into C++ functions in the engine using C# is only really faster for highly complex algorithms.

All four languages can be mixed in the same project as required. A script is merely attached to a node.

## User Input
[Input](https://docs.godotengine.org/en/stable/classes/class_inputevent.html#class-inputevent) is what really makes a game a game. In Godot there is the \_unhandled_input(event) virtual function that tells the engine what to do with these events. They can be found using the InputEvent node.

Alternatively, it is likely better to use the [InputMap](https://docs.godotengine.org/en/stable/classes/class_inputmap.html#class-inputmap) node to define what actions are assigned to what keys or buttons ahead of time. This also allows the engine to re-map keys at runtime.
