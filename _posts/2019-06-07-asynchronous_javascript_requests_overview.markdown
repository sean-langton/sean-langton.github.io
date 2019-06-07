---
layout: post
title:      "Asynchronous Javascript Requests Overview"
date:       2019-06-07 18:04:21 +0000
permalink:  asynchronous_javascript_requests_overview
---

Early web development was significantly limitied but the capabilities of HTTP Protocol. Early websites could only load data when specifically requested by the user. Pages were extremely static or required a plugin such as Adobe Flash. The main way to load a new view was by loading a new page.

*A traditional HTTP Request functions as follows*

1. Request is sent to the server.
2. While the server is processing the request, the client waits for a response.
3. Once the response is recieved, it is processed by the browser and a new page is loaded.

Being able to send and recieve data without reloading a page is a core requirement of almost any modern web application. This ability to transfer data in the background are handle via a javascript XMLHttpReques object or more simply a XHR object. Asynchronous JavaScript + XML, or AJAX, allows for websites to make quicker data requests and applications faster and more user-friendly. Despite technologies changing and JSON overtaking XML, the name still stands.

*AJAX functions as follows*

1. Request is sent to the server, with a callback function to handle the response once recieved.
2. While the response is being processed, a promise object is returned, allowing the page to continue loading.
3. Once the response is processed, the server returns the response object and the promise is resolved to this new object.
4. Callback functions are called using new this newly retrieved object, and the page is updated accordingly.

These request consist of three parts.

* **Type** - Either a GET or POST request
* **URL** - The URL to send the request to
* **Header** - Optional paramaters that can be used to inform the server how to handle the request or the client to handle the response.

AJAX is a concept that developed in the mid-2000s and was the backbone of websites like Facebook, Twitter, and almost any modern website. It allows a level of functionality that was previously only capable through standalone desktop applications. And while the technologies behind it may change over time, it is still the standard bearer for creating interactive websites.

