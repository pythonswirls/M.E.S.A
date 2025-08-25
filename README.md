(WIP) (Mem. Efficient State Automaton) Just a learning-focused research outline for designing a topological state machine automaton with neural net properties.


---
### Init. concept:

I have concocted an idea for a topological, logic-rigid state machine on a graph database that can emulate an LLM to a certain extent. One method used for learning scaling up the number of nodes in accordance with the unique control loop designed for creating new nodes.

Features will include:

* A graph DB with logic abstraction layers, each layer consisting of:
	* Node(s): (logic blocks synonymous with each other (somewhat) on that layer)
		* a configurable ADT struct/class defining:
			* the name of the concept the node represents on that logic layer
			* the framing of data passing through the node
			* how that data influences the weights/transformed into the output
			//// by this DB convention, there is memory allocated temporarily per node as node is passed over in a logic control loop
		* Input "pin"
		* Output "pin"
		//// UNIQUE PROPERTY: input/output pin per node can converge into one/split in multiple processes leveraging multiple threads in an resource balancing algo. For example, you can utilize a single node to define multiple instances of that control loop in memory/process space.
		* n number of "weight pins" (output "influences" or shifts decisions on mainly lower levels, especially where there is split decision-making)
		* link(s) connecting the output/weight pins to as many input pins as necessary
		//// "pins" are an idea that helps visualize nodes as if they were little black boxes in a bigger logic control loop. In reality, there is only a symbolic link to the next object (which will be initialized in memory soon), and the understanding that information in the current object will only be relevant when passed into the next object.
		//// not all nodes in the database will be initialized in memory at once; merely a couple at a time as the control loop is cycled
	* Node groups:
		* a struct of structs ( and name for that group)
		//// a way to further abstract logic on each logic abstraction layer (these bigger black boxes can be in parallel, series, or both)
	* Specialty nodes (for almost directly processing information from an external API
* Sensory input API's (highest possible layers)
* Long-term knowledge DB API(s) (logic control loops can dictate the use of functions read/write/erase from a separate DB. This is distinct for the contextual memory stored inside the state machine: modeled with the creation of new nodes corresponding to concepts, and the connection of those nodes to other nodes) (there is also most likely an rigid algo designed solely for attaching a node to closely related terms on that logic layer)
* Motor control API's (lowest possible layers, for allowing state machine to deliver actions based on input that has been ultra-filtered down the topology)
* A rigid C program for manipulating the main state-machine DB and API functionality
	* algos for resource management (mainly memory)

