#  Local Storage in Java Script
### Persistent local storage is one of the areas where native client applications have held an advantage over web applications. 
### For native applications, the operating system typically provides an abstraction layer for storing and retrieving application-specific data like preferences or runtime state, these values may be stored in the registry, INI files, XML files, or some other place according to platform convention.
### If your native client application needs local storage beyond key/value pairs, you can embed your own database, invent your own file format, or any number of other solutions.
### Cookies were invented early in the web’s history, and indeed they can be used for persistent local storage of small amounts of data. But they have three potentially dealbreaking downsides:
#### 1. Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over
#### 2. sending data unencrypted over the internet (unless your entire web application is served over SSL)
#### 3. Cookies are limited to about 4 KB of data — enough to slow down your application (see above), but not enough to be terribly useful.
## Introducing HTML5 Storage
### HTML5 Storage: It's refer to a specification named Web Storage,which was at one time part of the HTML5 specification proper, but was split out into its own specification for uninteresting political reasons.
### Certain browser vendors also refer to it as “Local Storage” or “DOM Storage”.
### What is HTML5 Storage: t’s a way for web pages to store named key/value pairs locally, within the client web browser.
### From your JavaScript code, you’ll access HTML5 Storage through the localStorage object on the global window object. Before you can use it, you should detect whether the browser supports it.
## Using HTML5 Storage
### HTML5 Storage is based on named key/value pairs. You store data based on a named key, then you can retrieve that data with the same key. The named key is a string. The data can be any type supported by JavaScript, including strings, Booleans, integers, or floats.
## Tracking Changes To The HTML5 Storage Area
### If you want to keep track programmatically of when the storage area changes, you can trap the storage event. The storage event is fired on the window object whenever setItem(), removeItem(), or clear() is called and _actually changes something_. For example, if you set an item to its existing value or call clear() when there are no named keys, the storage event will not fire, because nothing actually changed in the storage area.
## Limitations In Current Browsers
### The limitations of the now-standardized HTML5 Storageis:
#### 1.How much storage space each origin gets by default, which is 5 megabytes
#### 2.The exception that will get thrown if you exceed your storage quota of 5 megabytes, which is (QUOTA_EXCEEDED_ERR).
#### 3.The answer to the next obvious question, “Can I ask the user for more storage space?”, which is NO.
## Competing Visions
### While the past is littered with hacks and workarounds, the present condition of HTML5 Storage is surprisingly rosy. A new API has been standardized and implemented across all major browsers, platforms, and devices. 










