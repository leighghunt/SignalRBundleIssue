SignalRBundleIssue
==================

Test project illustrating ASP.NET MVC4 Bundling issue with SignalR

- Create new ASP.NET MVC 4 Web Application using Internet Application, Razor engine
- Add SignalR, following steps outlined at https://github.com/SignalR/SignalR/wiki/QuickStart-Hubs
- Package Manager :

````
PM> Install-Package SignalR
Attempting to resolve dependency 'SignalR.Hosting.AspNet (≥ 0.5.3)'.
Attempting to resolve dependency 'SignalR.Hosting.Common (≥ 0.5.3)'.
Attempting to resolve dependency 'SignalR.Server (≥ 0.5.3)'.
Attempting to resolve dependency 'Newtonsoft.Json (≥ 4.5.4)'.
Attempting to resolve dependency 'Microsoft.Web.Infrastructure (≥ 1.0)'.
Attempting to resolve dependency 'SignalR.Js (≥ 0.5.3)'.
Attempting to resolve dependency 'jQuery (≥ 1.6)'.
Successfully installed 'Newtonsoft.Json 4.5.10'.
Successfully installed 'SignalR.Server 0.5.3'.
Successfully installed 'SignalR.Hosting.Common 0.5.3'.
Successfully installed 'SignalR.Hosting.AspNet 0.5.3'.
Successfully installed 'SignalR.Js 0.5.3'.
Successfully installed 'SignalR 0.5.3'.
Successfully removed 'Newtonsoft.Json 4.5.6' from SignalRBundleIssue.
Successfully added 'Newtonsoft.Json 4.5.10' to SignalRBundleIssue.
Successfully added 'SignalR.Server 0.5.3' to SignalRBundleIssue.
Successfully added 'SignalR.Hosting.Common 0.5.3' to SignalRBundleIssue.
Successfully added 'SignalR.Hosting.AspNet 0.5.3' to SignalRBundleIssue.
Successfully added 'SignalR.Js 0.5.3' to SignalRBundleIssue.
Successfully added 'SignalR 0.5.3' to SignalRBundleIssue.
Successfully uninstalled 'Newtonsoft.Json 4.5.6'.
````

- Create a class that derives from Hub
- Created Javascript + HTML Client

- On starting application in Firefox, Firebug complains about ````$(function () {```` line in Index view, reporting:

````
TypeError: $ is undefined
http://localhost:54051/
Line 62
````

Resolution
==========
Remove duplicate JS file, and move bundle to head.
Resolves error, and signalr messages now getting through.

See 5cdfa63ca7353b7b4c2599114d3a7c4602dbd047
https://github.com/leighghunt/SignalRBundleIssue/commit/5cdfa63ca7353b7b4c2599114d3a7c4602dbd047