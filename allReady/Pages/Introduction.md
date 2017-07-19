# General details about the project  #

![All Ready](https://github.com/HTBox/allReady/blob/04456b9816ce918376e12d99c78bf434a444fed8/docs/media/all-ready-project-banner.jpg)

Humanitarian Toolbox (HTBox) is a charity supporting disaster relief organizations with open source software and services.  
HTBox harnesses the skills of volunteer developers to contribute disaster relief aid through

1.	Creating apps that map the spread of disease
2.	Maintaining software that helps to optimize the delivery of relief supplies
And more…

Humanitarian Toolbox has a goal of creating software and programs for relief organizations to have ready in times of need.
What makes HTBox unique is the focus on sustainability through the use of Open Source software. Developers want to give to charity using their skills – building software. 
There are other projects that build software solutions within a humanitarian organization during a crisis.  But, when the crisis is over, often the people involved in creating it move on or the software languishes on the shelf. Instead of deteriorating, HTBox takes on these projects so they can be maintained and ready for future usage. 


**allReady** is a sub project of Humanitarian Toolbox. its continuing mission, to harnnest the skills and capabilities of developers in order to maximize the value they deliver to society, or in their own words [[1]](http://www.htbox.org/about):

> A massive storm floods Manhattan - **and people need to find shelter quickly**.
> 
> Drought hits the Horn of Africa - **and smart delivery of food supplies saves lives**.
> 
> An earthquake rocks Mumbai - **and first responders need to know where to go minute by minute**.
> 
> Responding to disasters like these means boots on the ground—but we can help responders do more with less when we see them as coding challenges. Do you want to use your skills to do some good and learn along the way? Together a few sharp minds can save lives and make a real difference.


That's the mission of the Humanitarian Toolbox. It connects devs with organizations in need of there expertise. As a developer you can build the next generation of life-saving tools and refine them to meet new needs as they arise.  Humanitarian Toolbox maintain and deploy this ‘toolbox’ of solutions quickly to get them in the hands of those making a difference. Everything built is open-source and part of an open ecosystem so the tools can be adapted, integrated and deployed to particular situations as they evolve.

If you are a developer, software architect, database guru, designer, tester or software project manager, then sign up to be part of The Humanitarian Toolbox, a "volunteer army" of software experts willing to donate part of their expertise and time to help solve the technology issues that arise in enabling this open response community and help us develop the solutions required to support this community based response [[2]](http://blog.disasterexpert.org/2012/11/the-sandy-legacy.html)

*Based on [HTBox Vision]( http://www.htbox.org/about/our-vision)*

#	Why this project? #
The Constrains were:  
 1. Interesting - It was indirectly followed by one of the team members for several years (via podcast - [.net rocks](http://www.dotnetrocks.com) e.g. [episode 808](http://www.dotnetrocks.com/?show=808)  )
 2. Big & complex enough - This is rather hard to quantify - but [contributers](https://github.com/HTBox/allReady/graphs/contributors), [commits](https://github.com/HTBox/allReady/graphs/commit-activity) and [issues](https://github.com/HTBox/allReady/issues) implies it meets the requirement
 3. Actively developed on GitHub ([>700 PRs in last year](https://github.com/HTBox/allReady/pulls?utf8=%E2%9C%93&q=is%3Apr%20is%3Aclosed%20%20created%3A2016-01-01..2017-12-12))
 4. [Has Unit tests](https://github.com/HTBox/allReady/tree/04456b9816ce918376e12d99c78bf434a444fed8/AllReadyApp/Web-App/AllReady.UnitTest). According to the docs [All projects have some unit tests.](http://htbox.github.io/building-the-project.html).
 5. Commonly used by disaster relief organizations [[1](http://solutionscenter.nethope.org/case_studies/view/humanitarian-toolbox-visual-studio-online-used-to-energize-and-optimize-cro)]  
 
 On the down side, is does not seem to be missing documentation on first glance.  
 
 One last plus - it has a [welcoming introduction for new contributers](https://github.com/HTBox/allReady#how-you-can-help) [[1](https://github.com/HTBox/allReady/wiki/Solution-architecture)]


#	Model of development #

The allReady project was jumpstarted by volunteers at Microsoft and has been turned over to Humanitarian Toolbox to be maintained and improved by the technical community at large and ultimately deployed in support of organizations delivering preparedness campaigns everywhere.  
The initial launch of development for allReady started on 7/20/2015 during the Visual Studio 2015 release event.

Nowadays, allReady is an open source project, hosted by github, and welcomes contributions from the community.   
The allready repo holds issues of all types (simple bugs, new feature & requirements and architectural updates) upon which contributes can contribute to the project.  
A large portion of the code base was contributed in dedicated hackathons (check out the large peek in the [contributers](https://github.com/HTBox/allReady/graphs/contributors) page, which correspondence to the [NOV 2015 hackathon](http://www.appvnext.com/blog/2015/11/18/hack-for-a-good-cause-my-humanitarian-toolbox-hackathon-experience) ). 

In addition, in case of any issues with the codebase or other content in the repository are spotted - [HTBox owners](https://github.com/orgs/HTBox/people) are encouraging logging an issue and they will work with the contributor to solve it.

Contributes are accepted via Pull requests, and using [appveyor CI](https://ci.appveyor.com/project/HTBox/allready/branch/master)

On top of that, HTBox holds occasionaly hackathons [[e.g. 2016]](https://www.meetup.com/AZGiveCamp/events/233223409/) 

#	Review of available resources: #
1. [an episode about HTBox](http://www.dotnetrocks.com/?show=808) is available ([.net rocks](http://www.dotnetrocks.com))


## Solution architecture ##


[Review the solution and database](https://github.com/HTBox/allReady/wiki/Solution-architecture)
The allReady application is implemented as a Visual Studio 2015 solution that contains two projects:
-an ASP.NET Core project that serves the web site and admin portal
-a cross-platform Cordova app project
The web application also exposes REST APIs used by the mobile app to access data.


- [Web application](#web-application)
- [Cross-platform mobile app](#cross-platform-mobile-app)


### Web Application ###

An ASP.NET Core web application provides the front-end web experience for volunteers accessing the allReady web site and the portal used by administrators. The site is powered by ASP.NET Core 1.0 using .NET Core 1.0. Here's the landing page for the web site:


The web site relies on the following frameworks:

* Bootstrap: responsive layouts on mobile devices
* Font-awesome: scalable vector icons
* Hammer: gesture support
* jQuery: ubiquitous JavaScript library
* Knockout: MVVM bindings


### REST APIs ###
The same ASP.NET Core project also exposes a set of Web APIs which are part of the MVC framework. These REST APIs are used by both the web site and the Cordova mobile app.

### Data layer ###
Data is stored in a database that is accessed by the ASP.NET application using Entity Framework Core 1.0.

### Cloud services ###
The allReady web project is designed to be hosted in Microsoft Azure. The following services are used by this application when running in Azure:

* App Service Web Apps: hosts the web application.
* SQL Database: storage of relational data.
* Storage: storage of uploaded BLOB data.

### Authentication ###
Authentication of web site mobile app users leverages OAuth 2.0 with credentials from external authentication providers such as Facebook, Twitter, Google or Microsoft. Users can use their existing social media accounts to sign into the web site or mobile app. For more information, see Enabling authentication using external providers.

### Cross-platform mobile app ###
The mobile app project was added to the allReady solution as a Visual Studio Tools for Apache Cordova project.

* The client app relies on the following frameworks:
* AngularJS: extensible web app framework
  * Apache Cordova: cross-platform device deployment, including these plugins:
  * Whitelist
  * InAppBrowser
* BarcodeScanner
* Ionic: enhancements for Cordova apps
* Moment.js: working with date-time values
* The app accesses the Web API exposed by the web app for data access.

Users can sign-in with supported social providers such as their Facebook, Twitter, or Microsoft. You must configure each of these providers for the mobile app separately, as described in the next section.

--------
This project is part of the [JCE ASOSMA](https://github.com/jce-il/ASOSMA) project, and uses templates and ideas from the [viewpoints and perspectives book](http://www.viewpoints-and-perspectives.info/vpandp/wp-content/themes/secondedition/doc/registered/VPandP_Reference.pdf)   

