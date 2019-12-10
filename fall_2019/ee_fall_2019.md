### [Presentation slides](https://docs.google.com/presentation/d/19Gi6qvdddrxKpm5C6mPzxLQkS1loJMsnq5jjXHL4LS0)

# ![logo](https://raw.githubusercontent.com/OpenCircuits/OpenCircuits/master/site/public/img/analog/icons/logo.svg)

### Fall 2019

## Team:

* [![Rylan](https://github.com/Rylander77.png?size=150) Rylan Gupta (Project Manager)](https://github.com/Rylander77)
* [![Jonathan](https://github.com/Schmaj.png?size=150) Jonathan](https://github.com/Schmaj)
* [![Christopher](https://github.com/jumpingkangaroo.png?size=150) Christopher](https://github.com/jumpingkangaroo)
* [![Delaney](https://github.com/delaneyaqua.png?size=150) Delaney](https://github.com/delaneyaqua)
* [![Vincent](https://github.com/vincenthuang.png?size=150) Vincent](https://github.com/vincenthuang)

## Project Goals:
* Add analog componentry and functionality to OpenCircuits
* Add analog circuit analysis methods and tools 
* Incorporate interoperability between digital and analog components across both projects

## Semester Goals
* Build off the work and research done during last semester (Spring 2019) 
* Research and assess different approaches to circuit analysis techniques and solutions
* Develop plan to implement aforementioned solutions and / or utilize libraries to achieve the same goal

## Different Approaches to Circuit Analysis
* Building our own framework and algorithms - starting with nodal analysis for DC steady state circuits with resistors
* 

## NGSpice Summary
NGSpice is a popular open source circuit simulation library. It is written in C, and is used as the back-end for multiple popular commercial circuit simulators and design tools. NGSpice uses a modified BSD license that permits us to use it. It is very well documented, with a comprehensive manual that was updated as recently as September. The main section in this manual that will be relevant to us is the section on its use as a shared library.

### NGSpice as Shared Library
If we used NGSpice as a library, we would have a C wrapper that would take in the netlist of the circuit from our typescript code, translate this netlist into the structs that NGSpice uses, and  translate the output back into something that could be returned to our typescript code. Here, we are going to briefly go over some aspects of using NGSPice as a shared library, including the structs it uses, the netlist format, and the functions that would be called by our wrapper. 
#### Netlist Format
The basic netlist we would pass to NGSpice is an array of strings (char** in C). The first line in the netlist is the of the circuit. An example of this is ".TITLE Simple Resistor Circuit". The last line of the netlist is just ".end". The rest of the lines of the netlist are each a component of the circuit. In each line is an element name, the nodes its connected to, and any parameter values. 

The first part of the line is the element name. The first letter of the element name specifies the type of component, while the rest make up the unique identifier of the component. For example, a resistor could be R1, ROUT, Rin, etc.

The second part of the line are the nodes the elements are connected to. A node name is an arbitrary string, case insensitive, that does not start with a number. There must be one string that is named "0" that is used as the ground node. For most "classic" analog components, two nodes are specified.

The third part of the line is the parameter value. This is used to specify the resistance, capacitance, etc. SI prefixes can be used to specify sizes. For example, 1M is converted to 1,000,000 and 1u is converted to 0.000001. 

#### Struct Formats

#### Functions to Use

#### Simulation Types to Use