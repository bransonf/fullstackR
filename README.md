`This is a work in progress, but it may turn into a short book if there is interest`

If you find this interesting, you may also be interested in the book that Hadley Wickham is writing, [Mastering Shiny](https://github.com/hadley/mastering-shiny) While Hadley's book aims to explore the Shiny framework, this book aims to explore R as a mulitpurpose language for full stack application development, and does so using Shiny only as an introduction to full stack.

# fullstackR
So you want to build a full-stack app in R?

### What is R?
R is a multipurpose programming language, similar to Python. R was developed originally for statistical analysis, but thanks to a growing community, it is now useful for everything from general purpose scripting to - yes - full stack application development.

### What is full-stack?
Full stack is a programming paradigm in which an application accepts user interaction (usually via a graphical interface) and communicates with a server in order to return a result to the user. The segment that deals with user interaction is generally referred to as the 'front-end' and the logic that process this input to return information is generally referred to as the 'back-end'.

----
|Table of Contents| |
|---|---|
| Preface | So you want to build a full-stack app with R? |
| Chapter 1 | The Anatomy of A Web App: R Shiny |
| Chapter 2 | Extending Shiny |
| Chapter 3 | Alternatives to Shiny |
| Chapter 4 | Using APIs to Seperate Work: Intro to Plumber |
| Chapter 5 | Packaging and Deploying Apps: Docker and the Cloud |
| Chapter 6 | Desktop Apps |
| Chapter 7 | Mobile Apps |
| Chapter 8 | More Efficient Data: Intro to SQL |
| Chapter 9 | Adding Dynamic Users |
| Chapter 10 | Securing Your App |
| Chapter 11 | Building off of R |

## Preface
While it is possible to build full stack applications in R, it may not always be the right choice. Although some 
[companies are using R](https://github.com/ThinkR-open/companies-using-r), the R stack is among the least popular for full stack development. However, if you work in an environment where R is common (academia for example) and want to explore building applications, the R stack may be for you. It is also worth mentioning at this point that while you can build almost everything without leaving native R, you probably should not. R is incredibly capable with interfacing a variety of other languages (see Chapter 11) and doing so will greatly expand the capabilites of your application. Using SQL or other databases, for example, offers a more manageable and much quicker interface to large quantities of data.

## Chapter 1
The most common method available for creating web applications using R is Shiny. Shiny has come a long way since its inception, and many popular web libraries are being ported to Shiny. To get started with Shiny, it's recommended that you have an up-to-date installation of [RStudio](https://rstudio.com/products/rstudio/#rstudio-desktop). Using RStudio will allow you to quickly preview your application and poses many other benefits of using an integrated development environment.

R Shiny apps are made of two parts; a user interface and a server. Although it is possible to put these in a single `app.R` file, I strongly reccomend that you do not. As you will find, larger and more complex projects benefit the most from clear code separation. Instead you should use a seperate `ui.R` and `server.R` file. Naming is important, as Shiny will always assume your ui and server to have these exact names.

The `ui.R` file contains instructions for how to generate a webpage. This is practically no different than writing HTML if you're familiar.

The `server.R` file contains instructions for making calculations or computations based on user input. Typically, user input will trigger an action on the server side, and often return something back to the user.

You may think of the ui as the 'front-end' and the server as the 'back-end'. As such, it is generally best practice to do heavy computations on the server side. Your users, known as 'clients' may visit your website or use your application on any device. The server, however, you have control over how powerful it is.

## Chapter 2

Given the environments where Shiny is often used, dashboards are among the most common use cases. As such, there are many packages that allow for quickly prototyping, creating and deploying interactive dashboards. `shinydashboard` provides a standard ui library for making Shiny dashboards, and `plotly/dashR` bridges Shiny with the standard plotly framework.

Many other linkages have been created, such as `bsplus`, which adds support for some important elements of the bootstrap library. Or, `shinyjqui`, which adds support for elements from the jQuery library.

Other tools have been developed, such as `golem`, which aims to create a more organized pattern for developing very large Shiny applications.

`awesome-rshiny`





### Shiny Packages
`shinyWidgets`

### Intro to HTML/CSS
Styling
Fonts

### Intro to JavaScript

JavaScript is the language of the modern web browser. One of the strong suits of JavaScript is that it runs on virtually any device with a web browser. It is one of the most, if not THE most popular programming language today. In the confines of a browser, it has no access to system functions or file manipulation, but through products like Node.js, it can be used to write an entire application as well. The advantage to knowing JavaScript when developing R applications is 

If you'd like to learn the full workings of JavaScript, head to [javascript.info](http://javascript.info/)

Thanks to Dean Attali, `shinyjs` was developed, bringing JavaScript closer to Shiny than ever before. However, you may still want to know about the JavaScript API for R shiny applications. At its core, you can use JS to pass other inputs to your Shiny apps (Like raw keystrokes!) For more information about Shiny/JS integration, you can read more on the [Shiny blog](https://shiny.rstudio.com/articles/communicating-with-js.html)

`htmltools`
`htmlwidgets`
## Chapter 3

### The Foundation
At the fundamental level, the role of a server is to distribute and manipulate documents. Thus, it is possible to build an application with more control than using Shiny as a framework. The package `fiery` allows you to do just this.
`httpuv`

## Chapter 4

### What is an API?
### Why use an API?
### Introduction to Plumber

`tmobile/loadtest`
### OpenCPU, another R API Framework

## Chapter 5
`ShinyProxy`

## Chapter 6

In some environments, it may be preferable to release executable desktop applications as opposed to web-based ones. For one, by disconnecting your application from the internet, you reduce the number of possible security vulnerabilites. Or, you just may not need to share your application externally, in which case web hosting can be a wasteful expense. Of course you can always share applications using Docker containers, but even this has its limitations. In many environments, for example, users do not have the neccessary privledges (or perhaps requisite knowledge) to operate with Docker containers. Luckily, several packages exist, each with slightly different methods of abstracting the environment to the desktop.
`r-shiny-electron`
`RInno`
`DesktopDeployR`

### Non-Web-Based Apps

In some situations, it made be advantageous to develop the entire application agnostic to the web. In these situations, using other libraries for building applications may be to your advantage. `RGtk2` creates an API to the GTK framework and `gWidgets` is a linkage to several supported frameworks. QT and GTK are popular and widely regarded these days. If you have trouble picking a framework to begin with, I would choose QT.

## Chapter 7

Developing for mobile comes with a whole host of extra considerations. Not only do you have to consider the variability of screen sizes (and possibly orientation), but you should consider things like touch based interface, variable connectivity and caching.
At least a few of these things can be handled using a mobile-development framework like `shinyF7`, which is a linkage to the F7 mobile development library.

### Getting on the App Store
Getting on the app store is becoming increasinly difficult, but you may not want to be on the app store anyway. And here's why:

Unfortunately, if you still have a strong desire to get on the app store, you may have to write native apps. This is not something R is particularly well suited for.

### Sensor Input
One of the exciting parts about mobile development is all of the sensors embedded in most mobile devices today. In order to access these sensors, you will have to ask for user permission, so keep this in mind and take precautions as to how this data is stored and processed. One of the most useful pieces of information is a user's location. The `geoloc` package allows you to interface most browser APIs for geolocation. If you find GPS methods to be inviable, Google's mapping suite offers a geolocation API that uses connection to cellular towers and internet access points as a proxy for the client's approximate location. The `shinysense` packages enables access to a variety of other sensors as well.

## Chapter 8

If you're building on the R stack, it's fair assumption that it has something to do with data. Now while dataframes are great for interactive use, they are a serious limitation to application performance. Instead, by using SQL, you can increase performance exponentially.

If you have never used SQL before, do not be intimidated. First you will need to choose an implementation. SQLite, MySQL and postgreSQL are probably the most popular. SQLite is meant for local implementations and lightweight as the name implies. Postgres is becoming increasingly popular as it is both performant and open source.

The magic behind SQL is that by providing clues about your data, you can greatly increase the speed at which a query can be made.

Different implementations will vary, but the common data types are:
```
BOOLEAN
INT
BIGINT
NUMERIC
CHAR
VARCHAR
TEXT
```

Luckily, many implementations exist in R. The `DBI` package is at the core of many of these implementations.
You can read more at [db.rstudio.com](https://db.rstudio.com/)


`shinyStore`

## Chapter 9
`googleAuthR`

## Chapter 10

### Intro to Encryption
At some point, your application may deal with sensitive data. In such cases, you should encrypt the data before exchanging it with the server. There are several considerations you must make when encrypting data, but let us begin with a high-level overview of encryption. The `cyphr` package implements all the hashing algorithms you need to encrypt your data.

Encryption works by the science of cryptography. You pass data through a hashing algorithm. Common implementations are the `SHA` and `MD` family. Other implementations exist, but for most use cases you should use one of the secure hashing algorithms (SHA). Also note, `MD5` is generally recognized as insecure, so don't use it! This hashing algorithm maps data to a hash of a fixed length. In other works, it converts your data to a long, seemingly random string. Reversing the process is typically infeasible. Only by having the key used to encrypt the data may you decrypt it.


### Deploying behind HTTPS
It is important, especially when dealing with private data, that you deploy your web application with Transport Layer Security (TLS) enabled. This encrypts the data being sent to and received from the browser. It also verifies the integrity of the server-client connection. To put it simply, it's what puts the S in HTTPS. If you want security, you need it.

There are several ways to go about implementing TLS, but one of the most common is using a reverse proxy. In this configuration, the client browser connects to the server via a secured domain, and the information is subsequently forwared to and from your application. In order to accomplish this, you will also need a signed certificate. You can get a free self-signed certificate using Let's Encrypt.

## Chapter 11

### Other Languages
R offers the ability to interface a variety of other programming languages. Here, I will highlight some notable ones, and why you may want to integrate them with your application.

- Python
- C++
- JavaScript

Learning other languages has many other advantages as well. For example, JavaScript is currently in very high demand in the labor market.

R has incredibly good C++ support through `Rcpp`. Python can be interfaced through `reticulate` although you will need to have the python interpreter installed and direct to its path.

## Other Information
Notable Active Developers in the R Shiny Stack:
@JohnCoene
@daattali
@dreamRs
@ColinFay
@trestletech

## Demos
`rstudio - shiny demos`
`davidruvolo51/shinyAppTutorials`
`daattali - demos`
