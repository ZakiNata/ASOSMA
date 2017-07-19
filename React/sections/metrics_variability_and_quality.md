## Metrics, Variability and Quality Measures

In order to access code quality we chose to follow the chose to follow the forensic approach and metrics presented by [Adam Tornhill](http://adamtornhill.com/) in his book [Your Code as a Crime Scene](https://pragprog.com/book/atcrime/code-as-a-crime-scene). 

Following we will explain the approach, define a few of the metrics and apply them on the React code base, followed by a brief discussion. 

### The Approach

Static code analysis can only bring us so far. It only inspects a snapshot of the codebase and can surely bring results, showing the interplay of classes, finding [code smells](https://sourcemaking.com/refactoring/smells) or style deviations. The premise of the book is that code and system design changes over time, and by monitoring and analyzing exactly those changes we can discover trends previously not seen using only static analysis techniques.

### Hotspots
>If many people change a file often, it hase many reasons to change.. [violating the Single Rresponsibility Principle]
--Adam Tornhill

<img src="images/react-hotspot.png" alt="Hotspots map" width="400">

Like geographical crime hotspots help the police to pinpoint areas with higher probablity of a crime being commited, code hotspots indicate code areas, where a lot is happening. Modules, classes or files which change a lot have also a higher risk of brining in bugs and unintended behaviour. According to Adam Tornhill, it violates the [Single Responsibility Principle](https://en.wikipedia.org/wiki/Single_responsibility_principle), one of the core design principles of [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)) object oriented design. In contrast, part of the application which do not change that frequently can be an indicator for a rather stable and modular codebase. 

The react project has as of right now about **4.2%** of its code base marked as Hotspots with **18.8%** of all the development happening around this code. In order to get a better perspective, a (short comparison)[https://codescene.io/showcase] of other open source projects can help us bring the numbers in perspective:

| Project  | LOC  | # of Contributors  |  Hotspots (%)  | Development in Hotspotss (%)  |
|---|---|:---:|:---:|:---:|
|  Elasticsearch | 707,838  |  221 | **0.5** | **8.2**  |
|  Rails | 257,315  |  503 | **0.8** | **5.8**  |
|  ASP.NET | 332,076  | 123  | **2.2**  | **12.2**  |
|  *React* | *127,331*  | *483*  | ***4.2***  | ***18.8*** |
|  Numpy | 222,507  |  505 | **9.8** | **13.2**  |

It surely depends on other metrics such as number of contributors, project maturity, etc. While React's numbers seem not that high, compared to other frameworks such as *ASP.NET* or *Rails*, the percentage of hotspots seems to be rather high.

### Temporal Coupling

<img src="images/temporal-coupling.jpg" alt="Temporal Coupling Explanation" width="400">

<img src="images/temporal-coupling.png" alt="Temporal Coupling React" width="800">

### Complexity

<img src="images/complexity-trend.png" alt="Temporal Coupling React" width="800">

### Knowledge Maps and Organizational Structure

>...organizations which design systems ... are constrained to produce designs which are copies of the communication structures of these organizations
--M. Conway


<img src="images/owner-high.png" alt="High ownership" width="400">
<img src="images/owner-low.png" alt="Low ownership" width="400">


