---
layout: post
title:      "Asynchronous Javascript Requests Overview"
date:       2019-06-07 14:04:22 -0400
permalink:  asynchronous_javascript_requests_overview
---

Early web development was significantly limitied but the capabilities of HTTP Protocol. Early websites could only load data when specifically requested by the user. Pages were extremely static or required a plugin such as Adobe Flash. The main way to load a new view was by loading a new page.

*A traditional HTTP Request functions as follows*

1. Request is sent to the server.
2. While the server is processing the request, the client waits for a response.
3. Once the response is recieved, it is processed by the browser and a new page is loaded.

Being able to send and recieve data without reloading a page is a core requirement of almost any modern web application. This ability to transfer data in the background are handle via a javascript XMLHttpRequest object or more simply a XHR object. Asynchronous JavaScript + XML, or AJAX, allows for websites to make quicker data requests and applications faster and more user-friendly. Despite technologies changing and JSON overtaking XML, the name still stands.

*AJAX functions as follows*

1. Request is sent to the server, with a callback function to handle the response once recieved.
2. While the response is being processed, a promise object is returned, allowing the page to continue loading. This promise object is returned with a state of *PENDING* so that the application knows that the request is being processed
3. Once the response is finished being processed, the promise is updated to *RESOLVED*  if the request completed successfully or *REJECTED* if the request was unsuccessful.
4. A corresponding function is called based on whether the promise was resolved or rejected

These request consist of three parts.

* **Type** - Either a GET or POST request
* **URL** - The URL to send the request to
* **Header** - Optional paramaters that can be used to inform the server how to handle the request or the client to handle the response.

A XMLHttpRequests have an open, setRequestHeader, and send method. Examples below:

```
xhttp.open(method, url, async);
xhttp.setRequestHeader(header, value);
xhttp.send(*string if POST request*);


xhttp.open("POST", "demo_post2.asp", true);
xhttp.setRequestHeader("Content-type", "application/x-www-form-urlencoded");
xhttp.send("fname=Henry&lname=Ford");
```

This creates a need for a significant amount of additional code to allow for callback functions and error handling. Typically AJAX is utilized using either jQuery or a Fetch function

```
Jquery
$.post( "demo_post2.asp", {fname: Henry, lname:Ford}, function() {
  alert( "success" );
})
  .done(function() {
    alert( "second success" );
  })
  .fail(function() {
    alert( "error" );
  })
  .always(function() {
    alert( "finished" );
  });
	
Fetch
fetch("demo_post2.asp", {
    method: 'POST',
    body: JSON.stringify({fname: Henry, lname:Ford}},
    headers:{
      'Content-Type': 'application/json'
    }
  })
    .then(function() {
        alert( "success" );
    }).catch(function() {
        alert( "error" );
    });
	
```
This is typically simplied using Fetch API provided by Javascript 
AJAX is a concept that developed in the mid-2000s and was the backbone of websites like Facebook, Twitter, and almost any modern website. It allows a level of functionality that was previously only capable through standalone desktop applications. And while the technologies behind it may change over time, it is still the standard bearer for creating interactive websites.

Sources:
[w3schools](https://www.w3schools.com/xml/ajax_xmlhttprequest_send.asp)
[Fetch and Errors](https://www.tjvantoll.com/2015/09/13/fetch-and-errors/)
[jQuery](http://api.jquery.com/jquery.post/)

