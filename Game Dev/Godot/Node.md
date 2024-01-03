Nodes are the basic building blocks of a [[Scene|scene]]. Nodes use Signals to communicate with one another. Signals allow nodes to react to events happening to nodes without having to hardwire them. These signals are easy to implement using the [[Observer]] design pattern.

Node have a few characteristics:
- Name
- Editable properties
- A callback function to update on each frame
- They are extensible
- They can be added to other nodes

In a scene multiple copies of a node can be present. These copies are called instances. A specific instance shares the same properties as other instances but each instance can have their properties individually overridden.

These modifiable scenes act like templates for all other instances. If the scene for that node is modified and saved all instances will also be updated although any overridden values will remain.