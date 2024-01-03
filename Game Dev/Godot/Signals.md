Signals are used to communicate between nodes. They appear in the "Node" tab of the editor when a node is selected. Child nodes can be found using the get_node(name) function where name is the actual name the node has in the Scene tab.

To programmatically use signals the child node must be found and then its signal connected to by calling child.signalName.connect(callback). The arg for connect is the name of the callback to be executed when the signal is received.

Custom signals can be defined just like variables but instead of the var keyword they use the signal keyword. These custom signals will appear in the editor and can also take arguments. To use a signal you must call its emit function: customSignal.emit(args...). 