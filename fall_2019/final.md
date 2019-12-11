# RCOS Status Update

## Final Update

## Rylan Gupta


## This Semester's Accomplishments

As Project Manager of the OpenCircuits EE team, I have had a variety of different types of contributions this semester. 

To speak to personal work, I made some contributions to the Docker part of the project. My own contributions are:

- [Issue #383](https://github.com/OpenCircuits/OpenCircuits/issues/383) and [PR #384](https://github.com/OpenCircuits/OpenCircuits/pull/384): 
This couple of fixes, despite the small number of changes, were interesting bugs to research and troubleshoot. One of the things I wanted to achieve is fully explain, in depth, why I opened the issue and why I requested the changes I requested. The issue is very detailed and mostly contains the fixes I already knew would solve the issues. I would later use this issue as a reference for when new members request to open new issues and need guidance. While they didn't need to know what the solution to their bugs were, Issue 383 was the standard as it is very verbose and well researched. I detail the errors I see and under what conditions I see them in, which is very important in opening issues on bugs. Many issues on the repo are unfortunately very vague and don't give details on how to reproduce the issue or what the issue even is.

- [Issue #408](https://github.com/OpenCircuits/OpenCircuits/issues/408) and [PR #409](https://github.com/OpenCircuits/OpenCircuits/pull/409):
This issue and PR fixed the docker build not building correctly as gcc was not isntalled in the Docker repo. Similar to Issue 383, this issue is fairly well documented as to what is causing the issues I was seeing.

- [PR #427](https://github.com/OpenCircuits/OpenCircuits/pull/427): 
After assisting [@maybellekusumoto](https://github.com/maybellekusumoto) with [Issue #399](https://github.com/OpenCircuits/OpenCircuits/issues/399) and [PR #418](https://github.com/OpenCircuits/OpenCircuits/pull/418), I wanted to use her work in changing the behaviour of the Docker image. To instead host the server on default HTTP port 80, the Docker image could now be run with an IP, and users could connect to the server just using the server IP or other DNS resolution to that IP. Additionally, I minimized the layers created during the Docker build process and further optimized build caching.


Outside of my own commits to the project, I also mentored my team and others who needed help and guidance with getting started in learning about the project. This included teaching crash courses in git, javascript, and project structure, as well as troubleshooting initial setups and getting dependencies installed and setup so that developers could start digging into the project. Additionally, I instructed ideal ways to create issues using my aforementioned [Issue #383](https://github.com/OpenCircuits/OpenCircuits/issues/383). I most closely mentored [@maybellekusumoto](https://github.com/maybellekusumoto) in learning to code. As she had little coding experience, I spent time during small group and outside of the classroom teaching her how to make small contributions like adding an icon in the header using HTML5 and SCSS, as well as adding port and IP address flags for the server executable in Go.

As only two members of the EE team participated in RCOS for credit, it became difficult to reliably assign tasks to individuals. Many EE members understandibly prioritized their coursework over small group meetings, so assisting them in making sure they are able to contribute was a challenge. However, many team members were still able to make contributions concurrently with researching, as many members tackled issues and other contributions given that they had backgrounds in coding. Chris and I were able to put our research together into the [Wiki page detailing our research work this semester](https://github.com/OpenCircuits/OpenCircuits/wiki/OpenCircuits-EE-Fall-2019). My contributions to the wiki page are as follows:


_____




### [Presentation slides](https://docs.google.com/presentation/d/19Gi6qvdddrxKpm5C6mPzxLQkS1loJMsnq5jjXHL4LS0)


# ![logo](https://raw.githubusercontent.com/OpenCircuits/OpenCircuits/master/site/public/img/analog/icons/logo.svg)


### Fall 2019


## Team:

* [Rylan Gupta (Project Manager)](https://github.com/Rylander77)
* [Jonathan](https://github.com/Schmaj)
* [Christopher](https://github.com/jumpingkangaroo)
* [Delaney](https://github.com/delaneyaqua)
* [Vincent](https://github.com/vincenthuang)


## Project Goals:
* Add analog componentry and functionality to OpenCircuits
* Add analog circuit analysis methods and tools 
* Incorporate interoperability between digital and analog components across both projects


## Semester Goals
* Build off the work and research done during last semester (Spring 2019) 
* Research and assess different approaches to circuit analysis techniques and solutions
* Develop plan to implement aforementioned solutions and / or utilize libraries to achieve the same goal


## Different Approaches to Circuit Analysis

While these items are not necessarily mutually exclusive, here are different approaches that the team considered:

* Building our own framework and algorithms - starting with nodal analysis for DC steady state circuits with resistors. Go on to support for AC circuits with RMS analysis, and capacitors and inductors. Ideally, each framework is build to support the future stages of development. However, improvements could take a lot of refactoring, which is a trait the OpenCircuits project already suffers from.
* Server side analysis - using API calls fromthe browser to send circuit schematics to an analysis server, this would make implementation for the client very trivial, and would allow us to use existing tools, such as SPICE, for circuit simulation running locally on the server. However, this approach is not ideal, as we would like to have the entire project contained to a web browser client without the need for server - client communication outside of GCP.
* Open Source library / framework - Implementing an existing open source project into OpenCircuits EE could turn such an immensly challenging task into a task manageable for the likes of RCOS. With a framework / library / project with a simple enough API, OpenCircuits EE could utilize said library to do the underlying analysis. This would be ideal, given the scope of RCOS projects and goals that are achievable on a semester to semester basis.
* SPICE implementation - SPICE is a standard framework for circuit analysis, used in many applications such as PSpice, LTSpice, NGSpice, amongst others. SPICE is used widely in educational settings for electrical engineering, and SPICE analysis has been around since 1973.


## Spice Algorithm Research

While researching our own SPICE algorithm implementation, the following sources were used to get a sense of what our own implementation of SPICE would entail:

Rashid, Muhammad H.. SPICE for Power Electronics and Electric Power. CRC Press, 2017.

“SPICE Algorithm Overview.” SPICE Algorithm Overview, ECircuit Center, 2003, www.ecircuitcenter.com/SpiceTopics/Overview/Overview.htm.

Tuinenga, Paul W. Spice - a Guide to Circuit Simulation and Analysis Using PSpice. Simon &amp; Schuster, 1995.

Department of Electrical and Electronic Engineering of Imperial College London - EE 2.3: Semiconductor Modelling in SPICE Lecture: https://www.imperial.ac.uk/pls/portallive/docs/1/7292571.PDF 


## Libraries & Projects Considered

When considering projects, the following attributes were considered when researching each project:

- [ ] Language
- [ ] Documentation
- [ ] API support
- [ ] License
- [ ] SPICE 

### Circuit Sandbox

Source: https://github.com/willymcallister/circuit-sandbox 

Demo: https://spinningnumbers.org/circuit-sandbox/index.html 

- [X] Language: Javascript
- [ ] Documentation
- [ ] API support
- [X] License - MIT License
- [ ] SPICE 

The entirety of this projects analysis and component models are in [one 6912 line long .js file](https://github.com/willymcallister/circuit-sandbox/blob/master/js/schematic.js), making this a difficult project to easily understand and use. The project would be better off using a more organizaed project.


### Maxwell

Source: https://github.com/Aerlinger/maxwell 

Demo: http://circuitlab.herokuapp.com/

- [X] Language: Javascript
- [ ] Documentation
- [X] API support
- [X] License - MIT License
- [ ] SPICE 

Maxwell has a much better layout and organization than Circuit Sandbox. Additionally, the project has a real-time graphing logger, and many example circuits. While there is also some API functionality, the project shows signs of incompleteness, such as lingering TODO's and commented out code with no new commits in over 2 years. Ultimately, a more complete and perhaps actively developed library would be a better fit for OpenCircuits EE.


### circuitjs1

Source: https://github.com/pfalstad/circuitjs1 

Demo: http://www.falstad.com/circuit/

- [X] Language: Java, runs in [GWT](http://www.gwtproject.org/overview.html)
- [ ] Documentation
- [ ] API support
- [X] License - GNU GPL License
- [ ] SPICE 

Circuitjs1 also has a real-time graphing logger, and many example circuits. This project also has unique features, such as an audio output for signals, as well as simulation and current speed control. However, there is no API documentation.


### NGSpice

Source: https://sourceforge.net/projects/ngspice/ 

- [ ] Language: C
- [X] Documentation
- [X] API support
- [X] License - New BSD license
- [X] SPICE 

With a JavaScript wrapper for the C code, such as a GWT type project, node module, or WebAssembly, we could use the NGSpice C code in our project in the browser. NGSpice is widely used in many applications today, and is actively developed. There is also a lot of documentation for using the project as an API. 


### Conclusion from libray and project research

While a greater challenge than using an existing open source library written in JavaScript, the team decided that SPICE analysis. The following section details how we could use NGSpice in OpenCircuits EE moving forward.


