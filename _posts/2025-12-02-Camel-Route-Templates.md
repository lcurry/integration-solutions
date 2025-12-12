## How to use Route Templates to get more value out of your Camel Route  

This article is about a cool feature in Apache Camel that can help you create more flexible, re-usable integration solutions. The feature is called Route Templates and I will tell you why I think this feature is unique and will make the routes you create more flexible, reusable and maintainable. This ultimately means a more resilient and hardened integration solution. I will also provide a sample integration solution that uses the feature to define routes. 

---

### Why Apache Camel ?

If you've used Red Hat integration products you already know that [Red Hat's build of Apache Camel](https://docs.redhat.com/en/documentation/red_hat_build_of_apache_camel/latest) is something special.  Using it to build integration solutions can be a secret weapon for accomplishing most any integration challenge. Camel's feet are planted firmly into Fortune 500 businesses running many of the world's mission critical transactions today.  The developer's behind the Apache Camel community project are busy actively contributing new features and improvements. With so many integration frameworks out there, this project hits the right level of abstraction and remains the gold standard for integration and middleware development. 

There's a lot of talk about drag and drop integration, low-code and no-code platforms, and the "citizen integrator".  Red Hat's build of Camel has a story here too with [Kaoto](https://docs.redhat.com/en/documentation/red_hat_build_of_apache_camel/4.14/html/kaoto_camel_designer/index). While these tools can get you started fast and make for a great demo - they often fall short in facilitating most real-world integration challenges - without some "under the hood" coding and customizations. Camel offers the right level of abstraction for both a quick prototype, as well as the customization required for most any production-ready solution.  

### Introduction to Route templates 

This article assumes you already know what a traditional Camel route looks like. Camel routes consist of [a series of processing steps that are connected in a linear sequence](https://camel.apache.org/manual/routes.html).  You should be familiar with the Camel DSL (Domain Specific Language) that allows you to express integration patterns clearly and concisely.

I've built many traditional Camel routes to connect one system to another. Usually starting from scratch with good intentions. Perhaps using a [camel maven archetype](https://camel.apache.org/manual/camel-maven-archetypes.html) to lay down the code structure.  More often than not, by the time I'm done coding,  the "simple" route has become long and overly-verbose. I've added complex (yet necessary) logic into the route in order to meet quirky requirements of the systems being integrated. 

Route templates give me a framework for encapsulating that necessary complexity. I create the template that represents the integration scenario I'm trying to solve.  The template is parameterized so that it becomes instantiable. As a route template it then becomes re-usable, meaning I (or someone else) can create one or many new instances of the route. The materialized routes (based on custom parameters) allow you to realize the original template as a working solution.
 
### What's in it for me? 

Why would I want to implement my route as a route template? Whats in it for me and for others? For the developer of the template its not that much effort. As a developer, implementing your route as a route template is not very hard. You will take a slightly different approach to writing the code for your route than you would if you were writing a traditional route.  Others will benefit because it becomes much easier to re-use the (potentially complex) code you've written to implement future renditions of the integration scenario you originally solved.  Creating new instances of a route is as easy as crating a property file with key/value pairs. An end-user can create as many instances of the route and customize based on the parameters you've made configurable. All without writing a single line of code. 

### Creating Routes from a Properties File 

I'll start with the end in mind. Lets imagine I've developed a Camel route to consume purchase orders from a directory using the Camel [file](https://camel.apache.org/components/latest/file-component.html) component. Using [split](https://camel.apache.org/components/latest/eips/split-eip.html) Camel will split those files into sub messages based on individual line-items. Those messages will then be written to a JMS message queue. Note such a route sounds fairly trivial but when you start implementing you will soon notice the code complexity can grow rather quickly. 

Let's say my route is wildly successful and my boss wants the pattern re-used in lots of places throughout the organization.  
When you've take the time to implement your route as a route template, someone can now create your route in a very straightforward way without code, rather by configuration. 

Such that the following Spring properties file is all you'll need to instantiate routes based on your route template. 


(TODO image file of properties)

### Creating the route template - 


This configuration driven approach is externalized Route Definitions



### A More Useful Example 


### Summary 

Route templates provide a middle ground in terms of abstraction - 
between writing a completely custom route using traditional Camel DSL 
low-code and no-code myth when building enterprise-level applications


Perhaps your organization has need for some common integration patterns 

File to File
FTP to FTP 
HTTP to HTTP 
JMS to JMS 
JMS to File 


#### Some T-SQL Code

```tsql
SELECT This, [Is], A, Code, Block -- Using SSMS style syntax highlighting
    , REVERSE('abc')
FROM dbo.SomeTable s
    CROSS JOIN dbo.OtherTable o;
```

#### Some PowerShell Code

```powershell
Write-Host "This is a powershell Code block";

# There are many other languages you can use, but the style has to be loaded first

ForEach ($thing in $things) {
    Write-Output "It highlights it using the GitHub style"
}
```
