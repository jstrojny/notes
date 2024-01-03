A game made in Godot is a tree of Scenes. Scenes can really be anything: a character, a weapon, a menu, etc. Scenes can be nested under scenes, such as a player in a level.

Scenes are made up of individual [[Node|nodes]] which describe the behavior of a scene. A tree of scenes is also a tree of nodes.

Scenes work just like nodes because they are made up of nodes. When a scene is added to another node or scene the nodes it is comprised of are collapsed.

Nodes are **composed** to form scenes. A Godot project can have as many scenes as necessary but **one** scene must act as the main scene. The main scene is the entrypoint for the project.

Scenes have a few characteristics:
- There is always one root node
- They can be loaded and unloaded from disk
- There can be one to N copies of a scene