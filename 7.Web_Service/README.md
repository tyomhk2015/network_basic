# Web Service

### TLDR

Overall architecture or flow of web service, from primitive to current state.

### The Past of Web 📜

(Background)

Sir Timothy Berners-Lee: Creator of HTML, HTTP, and Web.

Papers, or documents, have many references to other paper for evidence. To read the reference, researchers had to physically find the specified materials for detailed information, which takes some time. To solve this problem, Sir Timothy Berners-Lee came up with HTML, text with linking attached, which enables to readers to read the references instantly from the paper the readers current were reading at the time.

To send HTML to internet efficiently, Sir Timothy Berners-Lee made a protocol called HTTP, which is a protocol for sending and receiveing HTML files via internet. Thanks to the internet and HTML, computer started to link each other and the numbers increase as time went by. The formation of linked computers looked like a spider web, and this was the moment the term 'web' start to become common. Therefore, HTML, internet, HTTP, these were also wrapped up as 'web'. Anything that is providing some helpful information with web started to be called as 'web service'.

```
Sir Timothy Berners-Lee (Researcher) → HTML → HTTP → Web
```

### Evolution of Web 📜

All the softwares that handles documents on the internet has three parts.
```
GUI + Logic + Data (Document)
CSS    JS*      HTML

*Mocha → Live → Javascript
*Runs on web browsers
```

The purpose of dividing a document / page into the 3 parts is for maintenance. If all 3 parts are mixed up together, it may take longer time to fix or update the document.

Personal Notes 🤔<br>
2022/05/06 - Currently, HTTP 1.1 is mainly used but there are a lot of shiftings from 1.1 to 2.0.

```
// Past web server

↑ Higher Level

Web Client ------- Internet ------- Web Server

          HTTP Request (w/ Method)
>---------------------------------------------
    (One-way communication / interaction)    |
<---------------------------------------------
                HTTP Response

<------------------- HTTP ------------------->
                  (Stateless)

<-------------- TCP/IP Connection ----------->
        (State Information is included)

↓ Lower Level
```

HTTP activates after client and server know each other's IP address and are connected with TCP/IP.

Once HTTP request is invoked from the client, there must be a HTTP response from the server, regardless of success or fail. 

Some of methods for HTTP requests are GET / POST / UPDATE / DELETE.
```
Create / POST
Read / GET
Update / PUT, PATCH
Delete / DELETE
```

The resources of the clients' requests are usually stored somewhere in the server's computer, like HDD or SSD. These resources are 'static'.

In contrast, creating and showing a new HTML with some visual changes when a user login can be called a 'dynamic' resource.

When the client visits some web site and response was successful, the server will return a HTML file with successed HTTP response code. The recieved HTML file will be handled by the browser that the client is using.
```
// Steps after browser recieving HTML file from server

1. Analyzes syntax of HTML file, Parsing.
2. Creates DOM tree, a.k.a data structure, by referring to the result of the analysis.
3. Start to render the page with given DOM structure.
4. Portrait / paint the page by referring to CSS file, matching DOM tree and the instructions on CSS. (Images get loaded after rendering DOM + CSS)
5. Apply javascript files to make the page more interactive.
```

Since browsers' main purpose is to view HTML pages, they can be called as 'remote page previewers'.


```
↑ Higher Level
                                                          (WAS)
Web Client ------- Internet ------- Web Server ---------- Logic ------------ Database
                                      Receive          Calculcation
                                      Response           Handler
                                                            |<-Keeping in touch*->|
          HTTP Request (w/ Method)
<---------------------------------------------
    (two-way communication / interaction)    |
<---------------------------------------------
                HTTP Response
↓ Lower Level

*Usually communicate with SQL.
```

Initially, the web server's role was not only to recieve and return requests to users, but also calculate some logics like 'login'. When the web started to interact in two-way communication, the handling logics or calculcation part got decoupled from web server.

In addition, states like 'before login', 'during login', 'after login' etc had to be stored somewhere. However, since HTTP was stateless communication and web server cannot keep track of the states, a technology called 'database' came into existence to solve the problem. On client side, to remember the state, 'cookie*' was introduced and became norm.

```
*Cookie: Consists of 'key' and 'value' properties with 'time limit' and 'range'.
```

### Web Application Server 📜

(a.k.a WAS)

```
// The three composition of web server.

                      (WAS)
Web Server ---------- Logic ------------ Database
Recieve            Calculcation
Response              Handler

                    Controller            Model

1-Tier---------------1-Tier---------------1-Tier (3-Tier Web Solution)
```

WAS<br>
* Web application server, or application server.
* Sometimes called as 'business logic'.
* A part of a server that provides extra features, handlings for incoming request. (e.g. middleware)
* Can be implmented with JAVA, Go, Node.js etc.

Common criteria for checking web server performance<br>
* Response Time of querying database. (Tuning)
* Response Time of HTTP request and response. (Status of network is crucial)
* Elapsed time of completing the business logics in WAS

System that monitors performance of the web server is called APM, application performance management system. (e.g. <a href="https://github.com/scouter-project/scouter">Scouter APM</a>). For business, <a href="https://jennifersoft.com/en/product/mainframe/">Jennifer</a>.

### Modern Web 📜

```
Web Client ------- Internet ------- Web Server

          HTTP Request (w/ Method)
>---------------------------------------------
                                             |
<---------------------------------------------
                HTTP Response
```

In the past, response of HTTP request was usually PC HTML files. However, in modern web, JSON became norm, which only has necessary data. I assume the background of this is due to rapid growth of smartphones. 

Returning PC HTML files to smartphones, Android or Apple etc, had possibility of compatibility issue, and creating an exclusive new view files for each smartphone device would not be very efficient. 

To tackle this problem, JSON was used just like headless CMS, where only minimal data is returned to desired devices in order to show a web page lowering chances of compatibility and efficiency issues.

Depending on the content or tech the developers use, the browser can dynamically create their own version of HTML that fits well to their own hardwares. (JS, React, Vue etc)

> RESTful API

Activate C.R.U.D operations by calling specific function, URI.


### Security Part

(Network hardwares are excluded from the content.)

```
                            1     2     3
Web Client --- Internet -------------------- Web Server
                          |IPS + SSL + WAF|
```

>IPS

Intrusion Prevention System

> SSL

Secure Socket Layer, encryption.

> WAF

Web Application Firewall
