This document describes the project's general code structure and provide some analysis for its current build and various views.
It also speculates its code-sturcture's integrity, though from an external point of view (through the analysis of an automatic tool) with no in-depth understandings of the project as one would get from personally working on the project.

[allReady documents](https://github.com/PhillipKatz/allReady/tree/master/docs)


About the documentation:
Currently, most of the introductions and documentations are left blank, with placeholders at every aspect except the installation guide, the git guide, and an unfinished event-starting guide.


Database: Web API written in ASP.NET connects with JSON

Stakeholders
=============
* **Assessors**, who check for compliance.
Working in tandem with the allReady staff, relying on their results and handing requests and feedback.
  * Red Cross: (Director: @Jim McGowan)

* **Communicators**, who create documents and training.
Most of the documents are yet to be written, with the exception of the "getting started" tutorials for volunteers, which were written by allReady's core-developers
  * Github contributors

* **Developers**, who create the system / Maintainers, who evolve and fix the system
  * ***Core developers***: Staff skilled in management, knowledgeable in programming; mainly in Web, SQL, .NET, and AngularJS
    *	Web team (Rohit, Elizabeth, Matt, Dan, Daniel, Glen, Connie)
    *	Mobile team: (Jimmy, Dmitry, Parashuram, Louis, Guillaume)
  * ***Volunteering coders***:
    * open-source contributors who volunteer to work on the improvement of allReady

* **Production Engineers**, who are responsible for the deployment environment.
 * Core developers: Staff skilled in management, supervising and directing the development of allReady; 
	Seth Juarez (technical)
	Dmitry Lyalin (Senior Product Manager)
	Brady Gaster (Program Manager)
	Kirupa Chinnathambi (Senior Program Manager)
	Pranav Rastogi (Program Manager)
	Tarvis Lowdermilk (UX designer)
	Zlatko Knezevic (Program Manager)
	Jeff Fritz (Senior Program Manager)
	

* **Suppliers**, who provide parts of the system.
External companies which provide tools/ professional advisory/ software infrastructure
Microsoft (contributing working platform, free server use and storage, and professional advisory and guidance) and various contributors

* **Support Staff**, who help people to use the system.
Technical staff, who help participants with hardware installation
Volunteers with various helpful skills during the emergency of unexpected disasters
Various others. For example, people who help raise readiness in a town by assisting in the installation of smoke detectors wherever the residents can't do so on their own

* **System Administrators**, who keep it running.
Main manager (Richard Campbell)
Advisors from Microsoft (backlog /pool / task-sharing management , operation monitoring and various logistics)

* **Testers**, who verify that it works.
Every programmer (core developer or contributor) is required to make his own test and make sure his addition / revision works well.

* **Users**, who have to use the system directly.
The organizations which physically deal with the disaster by aiding the locals, and the aided victims of the disasterous event.
Examples for emergency services: Red Cross, Police, Fire-fighters...
Examples for victims: people from towns caught in hurricane/earthquake/forest fires 


**Context Diagram**  
All of the involved parties around allReady
![context-diagram](https://github.com/turner11/ASOSMA/blob/master/allReady/imgs/Context%20Diagram.png)
The majority of allReady's views are involved with either git/github or Microsoft.


**allReady's Design**  

 
***allReady's data-flow design***  
Storage and flow of information  
![data-flow](https://github.com/turner11/ASOSMA/blob/master/allReady/imgs/data_flow.jpg)  
The database is shared between all supported platforms (mobile and web-browsers). The information is stored in Microsoft Philantropies' servers.  

**Dependencies**  
![dependencies](https://github.com/turner11/ASOSMA/blob/master/allReady/imgs/graph.png)
![slices](https://github.com/turner11/ASOSMA/blob/master/allReady/imgs/slices.png)
The code seems to be a bit tangled, though well-categorized.

Diagram conclusions:
The involvement of many volunteering free-time developers seems to be indicated by the high tanglement, while the well-separated categories (though their interaction is messy) may tell of a pre-determined architecture by well-coordinated managers. This result seems to make sense, considering the project's various views.
With this expected result, there's not much value to be derived from these graphs, as these problems are mostly unavoidable in such an environment. A proper fix should include an overall refactor of the code by the core-team.
All these conclusions are made from an external point of view according to Structure101's output diagrams, thus they aren't verified and have some room for error.




Challenges for this project
============================
* In all disaster scenarios, the system has to be at least as reliable as "pen and paper". Some disasters may render crucial infrastructures inoperable, thus suitable solutions have to be prepared ahead of time;
  - for example, in case internet connecivity is weakened or lost at the disaster site, allReady's data transfer can be disrupted and resumed. If necessary, vehicles with wi-fi are brought to the site to allow a complete transfer.
* Known bugs / issues:
  - Missing lots of docmunetation
  - [Individual volunteers are unable to contact the admins unless they are part of a registered organization](https://github.com/HTBox/allReady/issues/1929)
  - [Inconsistant naming in code](https://github.com/HTBox/allReady/issues/1940)
  - [In-app map does not support Internet Explorer](https://github.com/HTBox/allReady/issues/1550)
  - [Missing part in tutorial about sql handling](https://github.com/HTBox/allReady/issues/1844)
  - [Volunteers are not messaged / contacted yet in an ordered fasion](https://github.com/HTBox/allReady/issues/1842)
  
  
