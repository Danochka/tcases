# Tcases: A Model-Based Test Case Generator #

## What's New? ##

  * The latest version (Tcases 1.4.0) is now available at the Maven Central Repository. See [HowToDownload](HowToDownload.md) for download instructions. 

  * Introducing [Output Annotations](http://www.cornutum.org/tcases/docs/Tcases-Guide.htm#annotations): For an output transformation to produce concrete test cases, sometimes the basic information in the input model is not enough. You need to add extra information that is not important for generating the test cases but is necessary to form the final output. That's what output annotations are for.

  * JUnit output: To assist completion of test case code, Tcases now adds comments listing all input variable values in the Given section of each @Test method body. But if you prefer the previous output format, you can exclude these comments using the command line option `-p values=false`.

  * See [Troubleshooting FAQs](http://www.cornutum.org/tcases/docs/Tcases-Guide.htm#trouble) for more help on what to do when things go wrong. This includes more info on how to control Tcases logging output, including how to redirect logging to standard output. Also, logging messages have been improved to make it easier to understand what's going on.

  * Reducer: For better performance, reduce test cases for each function independently

  * Subscribe to the [Tcases Forum](https://groups.google.com/d/forum/tcases) group to get notifications and share experiences with other Tcases users.

## What Does It Do? ##

Tcases is a tool for designing tests. It doesn't matter what kind of system you are testing. Nor does it matter what level of the system you are testing -- unit, subsystem, or full system. You can use Tcases to design your tests in any of these situations. With Tcases, you define the input space for your system-under-test and the level of coverage that you want. Then Tcases generates a minimal set of test cases that meets your requirements.

Tcases is primarily a tool for black-box test design. For such tests, the concept of "coverage" is different from structural testing critieria such as line coverage, branch converage, etc. Instead, Tcases is guided by coverage of the input space of your system.

Tcases gives you a way to define the input space for your system in a form that is concise but comprehensive. Then Tcases allows you to control the number of test cases in your sample subset by specifying the level of coverage you want. You can start with a basic level of coverage, and Tcases will generate a small set of test cases that touches every significant element of the input space. Then you can improve your tests by selectively adding coverage in specific high-risk areas. For example, you can specify pairwise coverage or higher-order combinations of selected input variables.

## How Does It Work? ##

First, you create a system input definition, an XML document that defines your system as a set of functions. For each system function, the system input definition defines the variables that characterize the function input space.

Then, you can create a generator definition. That's another XML document that defines the coverage you want for each system function. The generator definition is optional. You can skip this step and still get a basic level of coverage.

Finally, you run Tcases. Tcases is a Java program that you can run from the command line or using the [Tcases Maven Plugin](http://www.cornutum.org/tcases/docs/tcases-maven-plugin/). The command line version of Tcases comes with built-in support for running using a shell script or an ant target. Using your input definition and your generator definition, Tcases generates a system test definition. The system test definition is an XML document that lists, for each system function, a set of test cases that provides the specified level of coverage. Each test case defines a specific value for every function input variable. Tcases generates not only valid input values that define successful test cases but also invalid values for the tests cases that are needed to verify expected error handling.

Of course, the system test definition is not something you can execute directly. But it follows a well-defined XML schema, which means you can use a variety of XML transformation tools to convert it into a form that is suitable for testing your system. For example, Tcases comes with a built-in transformer that converts a system test definition into a Java source code template for a JUnit or TestNG test class.

## Get Started! ##

  * [Tcases: The Complete Guide](http://www.cornutum.org/tcases/docs/Tcases-Guide.htm)
  * [The Tcases Maven Plugin](http://www.cornutum.org/tcases/docs/tcases-maven-plugin/)
  * [How To Download Using Maven](HowToDownload.md)
  * [Model-Driven Testing Using Tcases](ModelDrivenTestingForAgileTeams.md)
  * [Release Notes](ReleaseNotes.md)

## Contributors ##

Thanks to the following people, who have contributed significant improvements to Tcases.

  * Kerry Kimbrough (project founder)
  * Juglar
