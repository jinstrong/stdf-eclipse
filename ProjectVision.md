Open source tool for ATE Data Analysis

# Introduction #

On [LinkedIn](http://www.linkedin.com) a discussion was started by [Aparna Joshi](http://www.linkedin.com/profile?viewProfile=&key=6587116&authToken=JB9j&authType=name&goback=%2Eanh_941397) with the title "[Why do we need data files in STDF (Standard Test Data Format)?](http://www.linkedin.com/groupAnswers?viewQuestionAndAnswers=&gid=941397&discussionID=18344633&goback=%2Eanh_941397)"

The consensus is that although STDF is far from perfect, the good thing about it is that it is a **standard**. For any data manipulating tools to be used widely they **MUST** be based on a standard.

There are many good tools available on the commercial market, but none in the open source domain. As the prices for the nice commercial tools are high (or at least perceived as such) the existence of STDF itself is put in question over and over again (that's why the above discussion was started). This in turn doesn't help STDF to evolve, whereas there is clearly still room to do so.

This project attempts to get an open source effort up and running that will enable people to manipulate ATE LOG files in general, and STDF files in an inter-active way for **INVESTIGATION** purposes. It is **NOT** an attempt to compete with commercial tools!

# Implementation Choices #

## 1. Programming Language ##

A long discussion can be made on what programming language to use, and in fact each language has advantages and disadvantages for the task at hand. Now if we make for a minute abstraction of the language and ask ourselves what it is that we want to do, then the answer is :

  * Load some ATE data file into memory ( STDF / WAT / GDF / CSV / ...)
  * Extract data (summary, test list, ...)
  * Transform data (discard dies with bincode X, PAT, ...)
  * Calculate correlations
  * Create graphs (trend, distributions, XY scatters, ...)
  * Write data to file in some format ( STDF / WAT / inkmap / CSV / XLS / ...)
  * Create a report
  * ...

So, if we implement this project just by "choosing" a programming language, the project will fail, because it means that the user needs to be very familiar with the chosen programming language ... is this really what we want ???
It also means that things that have not much to do with the project also have to be programmed (revision control, project updates, report builder, ...)

The question thus is not what programming language will be chosen, the question is what IDE will be best suited for the tasks at hand ?

Now what should be the criteria to chose the IDE ?

  * Open source!
  * Multi platform! (Windows, Linux, Solaris, OSX, ...)
  * Plugin based architecture with integrated update facilities
  * Have a lot of plugins we can re-use
  * Have a big community so other people can easily join the project
  * Support testing of code (unit/integration/...)
  * Able to create an RPC (~stand alone program)
  * Multi language (English, Chinese, German, French, ...)

With those criteria we can look for the available IDE's on [wikipedia](http://en.wikipedia.org/wiki/Comparison_of_integrated_development_environments) ... and the usual suspects are ...

| IDE |  Home Page |
|:----|:-----------|
| [Kdevelop](http://en.wikipedia.org/wiki/KDevelop) | [![](http://upload.wikimedia.org/wikipedia/commons/4/48/KDevelop_icon.png)](http://www.kdevelop.org/) |
| [netbeans](http://en.wikipedia.org/wiki/NetBeans) | [![](http://upload.wikimedia.org/wikipedia/en/thumb/0/01/NetBeans.svg/150px-NetBeans.svg.png)](http://netbeans.org/) |
| [IntelliJ](http://en.wikipedia.org/wiki/IntelliJ_IDEA) | [![](http://upload.wikimedia.org/wikipedia/en/thumb/0/07/IntelliJ_IDEA_logo.gif/200px-IntelliJ_IDEA_logo.gif)](http://www.jetbrains.com/idea/) |
| [Eclipse](http://en.wikipedia.org/wiki/Eclipse_(software)) | [![](http://upload.wikimedia.org/wikipedia/en/3/34/Eclipse-logo.png)](http://www.eclipse.org/) |

Kdevelop falls off as it is written in C++, and C++ lacks [reflection](http://en.wikipedia.org/wiki/Reflective_programming) and also it has poor failsafe implementations.

The remaining candidates are all written in Java which does have reflection and a better failsafe implementation.

IntelliJ falls off as it has a proprietary license ... (pity)

Netbeans falls off as it doesn't seem to provide RCP support ...

This leaves us with Eclipse, and thus the programming language will be Java.

Let's not go into big discussions about "speed" because it is futile, and Java will be fast enough in any case because the speed penalty (once compiled, and hot-spot did his job) will be neglectable compared to the only other solution that was in the list, being C++.

Anyway now you have a good idea why the project elected ECLIPSE/JAVA as it's tools of the trade :-)









