**Angular Fundamentals** Pluralsight course wiki page

# Links
+ Pluralsight [Course page](https://app.pluralsight.com/library/courses/angularjs-fundamentals/)
+ [Files](https://github.com/joeeames/AngularFundamentalsFiles) from course creator
+ Built for version 1.0.5 and **updated for 1.4**. [Course on Angular 1.5 components](https://app.pluralsight.com/library/courses/building-components-angular-1-5/table-of-contents) is an update
+ ['Angular 2: First Look' course](https://app.pluralsight.com/library/courses/angular-2-first-look/table-of-contents)

# TOC
1. [[Intro|AngularFundamentalsIntro]]
2. [[Controllers & Markup|AngularFundamentals]]
3. [[Creating & Using Angular Services|AngularFundamentals]]

# Intro

## Course Introduction

Client-side JavaScript used to be simple enough that we could get away with very little thought as to the structure of our JavaScript, but as our web applications have become bigger and bigger, we need something to reign in all the resulting complexity. **AngularJS allows us to toss out all that client-side spaghetti code and write simple and elegant MVC-style single-page applications**. In module 1, I'll show you how simple it is to get your project bootstrapped with Angular and how to start working with Angular markup. Then, in module 2 I'll show you how to start _organizing that code into controllers_ and how to use the _built-in directives_ to _control your view_. Then I'll jump in, and in module 3 I'll show you how to _abstract some of the complexity out of your controllers and into services_ to **facilitate** the **single responsibility principle** and make testing easier. After talking about services, I'll show you in module 4 how to use routing to turn your app into a true single-page app, and I'll demonstrate all the built-in power and functionality that comes with Angular routing. And finally, in module 5, I'll talk about one of the most exciting and powerful pieces of AngularJS, directives. I'll demonstrate how you can use AngularJS directives to create your own custom elements, observe changes, and handle events. And last, but certainly not least, I will jump back in and show you how the Angular team has designed AngularJS to allow you to do all this in a fully test-driven way. I'll demonstrate how to test your controllers, services, and directives, and even how to do full end to end UI testing.

## Introduction to Angular

So what is Angular and why would you want to use it? The simplest answer to that question is that Angular is a **JavaScript library**, but it's so much more than that. It's probably more accurate to categorize it as an **MV* framework**. If saying that doesn't tell us everything about it, at least we have some context since we can compare and contrast it to some other popular MV* frameworks, such as **Knockout** or **Backbone**. Although we won't really make any direct comparisons to other MV* frameworks, we will discuss things it has in common with other frameworks, and the things that set it apart from the crowd. Angular isn't just an MV* framework, it's an **opinionated MV* framework**. What is opinionated software? Well, _opinionated software guides you into certain ways of doing things_. Opinionated software has a _vision_. It may limit itself to solving fewer problems, but generally, software with opinions solves those problems with less fuss. That doesn't mean that there isn't more than one way to solve a problem with Angular. For example, take DOM manipulation. _Angular wants you to_ **only** _manipulate your DOM inside of directives_, but with Angular inside of a directive you can use jQuery, Zepto, any other library, or even just raw JavaScript, to manipulate your DOM. That doesn't mean that you can't manipulate the DOM from within any other piece of an Angular application, but Angular definitely has an opinion about whether or not you should, and it gently guides you into doing things a certain way. So why should you use opinionated software? There are many reasons. At first glance it may seem like a lack of freedom is a bad thing, but that's really not true. The guys at 37signals, the company which invented Ruby on Rails, have written [a great article on the benefits of opinionated software](https://gettingreal.37signals.com/ch04_Make_Opinionated_Software.php). In essence, they say, the best software has a vision, the best software takes sides. This is quite true. You will find that using opinionated software will make it faster to do things that fall within the vision of the software. When it comes to Angular, that vision is extremely broad. It is well-suited to building anything from line-of-business applications to video players. In fact, if you are watching this video on your computer, then you are using an Angular application. But first, let's make sure that we understand exactly what an MV* framework is. The M in MV* stands for Model. **The model is where you store the data and state of your application**. The V in MV* stands for View. **The view is where you actually render to the user** the information that you want them to see, and the view is where your receive input from the user. The * in MV* stands for, well, something else. In many common MV* frameworks, the * is either a **controller**, or a **presenter**, or a **ViewModel**, or even something different besides those three. In fact, some frameworks even allow you to choose one of those three, and don't necessarily prescribe which one. Now you may be asking yourself, which one of those does Angular use? Well, **Angular uses a controller**. So some people may call Angular an MVC framework that would definitely be true, but in the web world there are so many frameworks that fall within this categorization, but don't necessarily fit into just MVC, that this term MV* is commonly used. Angular is an _open source library_ built by the folks at _Google_. This gives us the best of both worlds. It is maintained by a team of highly-skilled professionals whose employment is based around building Angular. That means that you won't have to worry about it stagnating because the primary contributors get bored or busy, but because it's open source, it can benefit from the contributions of the entire JavaScript community. In fact, at the time of this recording, Angular has over 100 unique contributors to its GitHub repository. Angular is also comprehensive. What makes Angular comprehensive? Let's take a look at a diagram. Angular **handles the Ajax communication with your server** so that you can _both send and receive_ data from your backend. This data is **stored as plain JavaScript objects**, so you won't have to make any special calls like get and set when you to update your data. Angular handles showing that data on the page, which you can do using **partial templates** or just _modify the HTML DOM that already exists_. Angular also **handles updating the data or model based on user interaction**, so when a user types into a text field, that new value can automatically be copied into your model. You don't have to wait for certain events, you can just tell Angular that a certain textbox owns a certain piece of data, and it will keep them in sync. This feature is called **two-way binding**. And lastly, Angular handles routing, or moving from one view to another. This is the key piece in building single-age applications or SPAs. This way you can completely change your view based on user interaction with your page. Angular will also update the URL in the browser so that the new view can be bookmarked for later. The next important aspect of Angular is its _testability_. Angular was built from the ground up with testing in mind. When the Angular team built the first versions of Angular, testability was a primary consideration. That means that Angular not only **supports isolated unit tests**, but it also **supports integrated end to end tests**. Also, a lot of the built-in objects that Angular provides have special versions that you can use to make your testing easier. In fact, testing is so critical to Angular, that while building the framework the team created a fantastic testing tool which used to be called **Testacular**, and is now called **Karma**. This tool is used by lots of development shops to test their code, and many of them aren't even using Angular. Perhaps the one attribute of Angular that sets it most apart from the rest of MV* frameworks is the fact that it **extends HTML** by _providing its own elements and properties_ called **directives**, that are used to interact with your HTML DOM. Basically, Angular lets you teach your HTML new tricks. Imagine if HTML had been **designed for applications** and not for documents. That is how Angular thinks of HTML and the ability it gives you to teach your HTML new tricks is a result of this thinking. 
`<input id="id1" type="text" focus>`
Here I have a simple input tag, but look at this last property. This is a custom attribute that I might build that tells Angular to make the element have focus when the page loads. What some of you may recognize is that HTML5 already has an attribute like this, it's called `auto-focus`. So HTML5 is already thinking along these lines. The problem is that that property only works in newer browsers. A custom directive like this one can work in a much wider range of browsers through the magic of Angular. Here's another example. This time I'm being a little more ambitious. 
`<multiStateButton id="btn1" />`
This is maybe a toggle button or possibly even a button that cycles through several states, but here I can create some kind of a multiStateButton that works the way I want it to work in my application. In my HTML, all I see is this, but after Angular gets done processing this element, the browser will see the HTML that it needs in order to accomplish what I want. And finally, something even more ambitious. 
`<userTile id="ut1" user="currentUser">`
This is, perhaps, a display widget customized to a particular application that displays users in a specific manner. I just have to pass in a user object using the user property that I created on my custom tag, and Angular knows how to turn this custom HTML element into HTML that my browser can render. Think of how this keeps so much of your view logic where it belongs, in your view. The last important attribute of Angular that we will discuss is how it is forward thinking. Angular is basically supporting the future of what we will see in web technology in the coming years, and as that technology becomes more widespread, our Angular applications will already be built to take advantage of that technology. Let's look at a couple specific technologies that apply here. Remember when I talked about what HTML would be if it had been designed for applications and not for documents? Well that's what web components are. **Web components allow you to make truly encapsulated components and widgets for your page, encapsulating HTML, JavaScript, and CSS**. [You can look at this article for more information about web components](https://www.w3.org/TR/components-intro/). Another up and coming feature that will soon be supported by some browsers is `Object.observe`. This technology lets you watch an object or a property on a JavaScript object for changes and react to those changes. Most MV* frameworks make you stick your data into special structures and call methods whenever you want to read or write to that data. Because Angular doesn't do that, it can support Object.observe when it becomes widely available, and Angular will simply benefit from the performance improvements of having things handled by faster, lower-level code. [You can read more about Object.observe at this URL here](http://wiki.ecmascript.org/doku.php?id=harmony:observe). 

Now one of the last things I want to do is take a quick look at Angular's official site. On the home page there's a lot of introductory text about it. There's this Learn section which has links to videos, and tutorials, and case studies, and a link to the Seed project template, which we will cover later on, but a key piece of the Angular site I want to show you that you're going to use and refer to a lot is under this Develop link, and it's these two links right here, the [Developer Guide](https://docs.angularjs.org/guide) and the [API Reference](https://docs.angularjs.org/api). Let's look at the Developer Guide first. This page has a list of all of the concepts that are part of Angular, so anytime you have any questions about something specific to Angular, you can come in here, look for the concept, say we have a question about modules, come in here, click on Modules, and look at Angular's official documentation on modules. Now let's look at the API Reference. This page has a list of a lot of the very specific pieces of Angular, for example, a list of all the directives that Angular provides is given right here. If we scroll down a little bit we can see a list of all the filters that Angular provides, and a list of all the services that it provides, and a lot of other stuff. So those are two pieces of Angular's official site that you ought to be comfortable with and visit frequently. Let's review with a quiz. _Angular thinks of HTML as if it had been designed to do what? Angular thinks of HTML as if it had been designed to build applications instead of documents. What kinds of tests does Angular support? Angular supports both unit tests and integrated end to end tests. Name one of the ways that Angular is forward thinking. Angular is forward thinking because of its future support for web components and Object.observe._

## Angular Architecture

Let's take a look at some of the architectural choices that Angular has made. First, Angular supports **two-way binding**. This means the user input into form fields is instantly updated in your Angular models. That means that in most cases you don't need to watch for specific events and respond to them, and then manually update your HTML. Instead, Angular will handle that for you. Angular also employs a technique called **dirty checking**. The net result of this is that you don't have to put your data into special structures and call getter and setter methods to read and write to your data. you can simply put your model data into plain old JavaScript objects and Angular will respond whenever your data changes and automatically update your view. Lastly, Angular is **built on dependency injection**. This lets you encapsulate pieces of your application better and also improves testability. You can read more about dependency injection here. 

Now let's take a look at the primary components of Angular and their relationship to each other. With Angular, _everything starts with the controller_. The **controller** is the **central player** in an Angular application. Controllers contain both _logic_ and _state_. Next we have the View. **Views are made up of bindings and directives**. This is how Angular talks to and listens to the user. _Controllers can communicate with views through both one-way and two-way binding_. _Directives_, which are a heavily talked about piece of Angular, are _really just part of the view_. And the last major piece is Services. **Services give you a place to contain the real logic and state of your application**. If you think about what is the essential tasks of your application, this would likely happen in your Services. Complex business logic, important application state, etc., Services are the place to house all that. Also, _Services are the place where you will want to communicate with the server_. Alright, let's review. What is the central component in an Angular application? The _central component_ in an angular application is the **controller**. _Directives_ are a part of which component? **Directives are part of the View**. In which component should you put your complex _business logic_? You should put your **core business logic** in the _Services_.

## Demo: Hello World in Angular

In this section, I'm going to build the simplest possible Hello World application that I can using Angular. If you look at my screen, you can see that I've got a minimal project with one file in it, an html file, and inside of that html file I've got a very small amount of HTML. I'm going to start by adding a script tag to point at the Angular library, and I'm going to point at the Angular library on Google CDN. I'm going to use version 1.4.0, which has been recently released, but you can use the latest stable version of Angular. Now that I've got that script file here, the next thing I need to do is tell Angular that this html page is an Angular application. I'm going to do that by going up to the _html tag_ and **adding an ng-app attribute to the html tag**, and I'm going to set it equal to "app". This is going to be the **name of my application**. Now that I've got that in place, the next step will be to add some HTML will display our Hello World message, so down in the body I'll add an h1 tag and I'm going to do two things to that `h1` tag. First I'll give it a special _attribute_ called `ng-controller`, and I'm going to set that equal to the value of `HelloWorldCtrl`. This will be the name of the controller that I'll create in just a second. And inside of that h1 tag, I'm going to make the **content two curly braces**, which tells Angular to replace this value with something else, and then I'm going to give it the value of `helloMessage`. That will cause Angular to look for a helloMessage variable and put its value inside this h1 tag. Now I've got to write a little bit of custom code and create this controller, which I named HelloWorldCtrl, and then create the helloMessage property. I'll do that by creating a new `script` tag, and inside of that I'm going to call `angular.module`. **This creates a module which is a container for every piece of an Angular application**. The first parameter of this function is the name of the module, which is going to be "app", which matches the name I gave it up in my html tag, and the second parameter is a _list of other modules that this module that I am creating depends on_. In this case, I'm not depending on any other modules, so I'm going to give it an _empty array_. Now that I've created the module, I can call the controller function, which will create a controller, which takes in two parameters. The first is the name of the controller, which is going to be HelloWorldCtrl, which matches the name I gave it in my h1 tag, and the second parameter is a function, I'm going to put this on another line to make it easier to read, and I'm going to have that function receive one parameter called `$scope`. This is a special parameter which we'll talk about more later on. And inside of here I will call $scope and create a new property called helloMessage, which matches the value that I put inside the curly braces on my h1 tag, and I'm going to set it equal to the string Hello World. And now if I open up that file in a browser, we will see the message Hello World.

## The Angular Event Reg Application

In this course, we will be learning about Angular through building a real application. This application is called Angular EventReg. Now we're not talking about some simple Hello World application. This application will have a reasonable amount of features. When we are done, we should have written around 500 lines of JavaScript and 200 lines of HTML, plus tests. Now realize that this is a showcase application and not necessarily a reference application on best practices, especially for things that are external to what Angular itself actually handles, such as CSS, deployment, data access, performance, and other concerns like that. We will be showing quite a few best practices with Angular itself, but as Angular is relatively new, many best practices are yet to be discovered and Angular is evolving all the time. New versions are regularly release, and with each new version new best practices are waiting to be found. One of our goals here is not to just teach you how to use Angular, but how to use Angular in a real-world application. This should give you the confidence you need to go and start your own Angular application from scratch. Now let's look at the major features of EventReg. EventReg is an application for _creating and viewing Angular events or conferences_, and for viewing and voting for the sessions available at these events. So the first major feature of EventReg is the ability to show a list of Angular events. From that list, the user can click on an event to see that event's details including a list of sessions and the details on each session. Also users should be able to create new sessions and events. There will be some validation here so that the necessary information is available on each event. Users who create an event or a session should be able to edit that event or session. Next, any operations that require knowing who the user is should require the user to login. As such, users should be able to freely register a new user account, and should be able to edit their account. Since we want to have a realistic application, we are going to be sending data to and from a server, therefore we will need some kind of server technology in place. You can really use any technology that you want, but in this course we will show you how to build and use both a node server and an ASP.NET MVC server, if you're on Windows. Of course the node server will run on both Windows and Linux. We will be making Ajax calls to the server just like we would in a real application, so it will show us what it's like to run Angular in a more production-like environment. For this application we will be using Twitter Bootstrap to make the styling easier. In addition, we will be using an open source theme for Bootstrap so that we have a slightly more interesting look and feel.

## Angular Version

This course was originally authored using Angular version 1.0.5. Since then, several major versions of Angular have been released. The current version of Angular is now 1.4. We have updated the course to be compatible with this version. In order to make the updates as seamless as possible, we have gone through all the demos and updated them to be compatible, and we've also gone through the entire course and updated it for 1.4. In some cases, those updates involved a complete rerecording of a clip, and in some cases the changes were minor enough that we simply added an explanation that was different, or left the clip alone. So it's possible that you might occasionally see a place where it looks like we're using version 1.2 or 1.0. You can safely ignore this, the course is up to date for 1.4. As newer versions of Angular come out, we will continue to update the course to be compatible with those versions. If you're following along, you should almost always be using the latest stable version of Angular. That might be 1.5 or even 1.6. You should always check the GitHub repo mentioned earlier, which will tell you if anything is out of date, but otherwise you can use the latest stable version of Angular.

## Tools Used

In this course, you will see a lot of work done from the command line. Although we recorded this course using Windows boxes, we are going to be using the Bash Shell for our command line work. For those of you who have only developed on a Windows Box it may seem a little foreign, but even though it may look a bit different from the Windows command prompt, you can follow along using either the standard Windows command prompt or the Bash Shell. None of what we do will be unique to the Bash Shell, and there will be only 1 or 2 places where the commands you use won't be exactly the same. In those cases we will note the difference. Most of our command line work will be running prebuilt scripts. From the Bash Shell we will run scripts that end in the sh extension. **For Windows users, you'll be using batch files**. If you have the downloaded code, you can choose between the .sh and .bat files based on your chosen command shell. If you're wondering how we installed the Bash Shell on Windows, it is installed when you install Git for Windows. The editor you will see us use in this course is Webstorm. Webstorm is a product by JetBrains, the same folks who make IntelliJ and ReSharper. The reason we chose Webstorm is because it is an excellent product. It gives you a lot of the features that you can't get from most text editors, but it's lighter weight than a full IDE like IntelliJ or Visual Studio, and it's integration with the Karma testing tool is second to none. You'll get to see that in the last module. Naturally, any text editor is fine to follow along. Nothing we do will be dependent on Webstorm. The last tool we need to talk about is the web server. As mentioned previously, you can use any web server that you want. In this course, though, we're going to show you how to create and use two different web servers, a Node web server and an ASP.NET MVC web server. You are free to use whichever one suits your purposes best, or if you're very familiar with another technology you're free to create your own. The web server that we're going to use is very simple. The web server itself will be responsible for not only serving up the files that we create, but also we're going to be sending and receiving Ajax to that server. In order to save that data, we're just going to write it to the hard disk, so therefore requests will come from the browser to the web server, which will then persist the data to the hard disk and correspondingly pull the data from the disk and serve it down to the browser when requested. Files relating to the web servers will be available on the GitHub repo for this course.

## Summary

In this module we started by taking a look at JavaScript MV* frameworks, some of the various options there, and how Angular fits into that world. Then we looked at some of the benefits of AngularJS such as it being forward thinking and very testable. After that we took a brief look at the application that we will be building throughout this course, the EventReg application.

---
# Controllers & Markup

---
# Services



[<<](AngularJS.md) | [Home](https://github.com/illegitimis/Tutorial/)