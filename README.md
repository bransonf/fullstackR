`This is a work in progress, but it may turn into a short book if there is interest`

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
`shinyjs`
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

### R Packages
`r-shiny-electron`
`RInno`
`DesktopDeployR`

### Non-Web-Based Apps
`RGtk2`
`gWidgets`

## Chapter 7
`shinyF7`

### Getting on the App Store
Getting on the app store is becoming increasinly difficult, but you may not want to be on the app store anyway. And here's why:

Unfortunately, if you still have a strong desire to get on the app store, you may have to write native apps. This is not something R is particularly well suited for.

### Sensor Input
`geoloc`
`shinysense`

## Chapter 8
`shinyStore`

## Chapter 9
`googleAuthR`

## Chapter 10

### Intro to Encryption
At some point, your application may deal with sensitive data. In such cases, you should encrypt the data before exchanging it with the server. There are several considerations you must make when encrypting data, but let us begin with a high-level overview of encryption.

`cyphr`
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
