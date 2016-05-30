﻿# Microsoft Application Insights JavaScript SDK

[Application Insights](https://azure.microsoft.com/services/application-insights/) tells you about your app's performance and usage. By adding a few lines of code to your web pages, you get data about how many users you have, which pages are most popular, how fast pages load, whether they throw exceptions, and more. And you can add code to track more detailed user activity.

## Try Application Insights with JavaScript SDK - no Azure subscription required
If you don't have an Azure subscription and would like to try Application Insights on one of your own web pages, visit [Try Application Insights Now](http://aka.ms/ainow). 

## Get started

To use this SDK, you'll need a subscription to [Microsoft Azure](https://azure.com). Application Insights has a free subscription option.
In the [Azure Preview Portal](https://portal.azure.com), create new or open an existing Application Insights resource.

### Initialize dynamically for MVC application using `snippet`
Get "code to monitor my web pages" from the Quick Start page, and insert it in the head of your web pages.  
[Learn more.](https://azure.microsoft.com/documentation/articles/app-insights-javascript/)

### Import as npm module and initialize dynamically
* Obtain instrumentation key from your Application Insights resource  
* Install applicationinsights-js with npm  
`npm install applicationinsights-js` 

* Import and call `downloadAndSetup` to initialize it. Note that you can override default CDN path of the script (for example, if you would like to host it locally) by specifying url parameter 
```
/* import AppInsights */
import {AppInsights} from "applicationinsights-js"

/* Call downloadAndSetup to download full ApplicationInsights script from CDN and initialize it with instrumentation key */
AppInsights.downloadAndSetup({ instrumentationKey: "f2c1b11a-e3ec-4d3a-b96b-xxxxxxxx" });

/* example: track page view */
AppInsights.trackPageView(
    "FirstPage", /* (optional) page name */
    null, /* (optional) page url if available */
    { prop1: "prop1", prop2: "prop2" }, /* (optional) dimension dictionary */
    { measurement1: 1 }, /* (optional) metric dictionary */
    123 /* page view duration in milliseconds */
);

/* example: track event */
AppInsights.trackEvent("TestEvent", { prop1: "prop1", prop2: "prop2" }, { measurement1: 1 });
```

## API reference

Data on users, page views, and exceptions are provided out of the box. You can write your own code to track specific events and metrics.

See:

* [JavaScript API reference](https://github.com/Microsoft/ApplicationInsights-JS/blob/master/API-reference.md)
* [API overview with portal examples](https://azure.microsoft.com/documentation/articles/app-insights-api-custom-events-metrics/)

## To build:

* Visual Studio 2013 Ultimate with Update 4 or later
* Clone the Git repository 
* Open Visual Studio solution (devenv JavaScript\Microsoft.ApplicationInsights.JavaScript.sln)
* Build solution in Visual Studio

## To run check-in tests
* `powershell "& .\RunTestsInBrowser.ps1"` to run `Tests.html` in a browser (you might need to call Set-ExecutionPolicy to be able to execute the script)
* Don't forget to build the solution after changing TypeScript files
* Refresh Tests.html in the browser to re-run tests

## Check out the Wiki for other useful info

https://github.com/Microsoft/ApplicationInsights-JS/wiki

## Contributing

We strongly welcome and encourage contributions to this project. Please read the [contributor's guide][ContribGuide] located in the ApplicationInsights-Home repository. If making a large change we request that you open an [issue][GitHubIssue] first. We follow the [Git Flow][GitFlow] approach to branching. 

[ContribGuide]: https://github.com/Microsoft/ApplicationInsights-Home/blob/master/CONTRIBUTING.md
[GitFlow]: http://nvie.com/posts/a-successful-git-branching-model/
[GitHubIssue]: https://github.com/Microsoft/ApplicationInsights-JS/issues
