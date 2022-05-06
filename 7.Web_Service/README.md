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

### Current Web 📜

All the softwares that handles documents on the internet has three parts.
```
GUI + Logic + Data (Document)
View / Controller / Model
```

The purpose of dividing a document / page into the 3 parts is for maintenance. If all 3 parts are mixed up together, it may take longer time to fix or update the document.

Personal Notes 🤔<br>
2022/05/06 - Currently, HTTP 1.1 is mainly used but there are a lot of shiftings from 1.1 to 2.0.

```
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

↑ Lower Level
```

HTTP activates after client and server know each other's IP address and are connected with TCP/IP.

Once HTTP request is invoked from the client, there must be a HTTP response from the server, regardless of success or fail. 

Some of methods for HTTP requests are GET / POST / UPDATE / DELETE.
```
Create / POST
Read / GET
Update / UPDATE
Delete / DELETE
```

The resources of the clients' requests are usually stored somewhere in the server's computer, like HDD or SSD. These resources are static.

When the client visits some web site and response was successful, the server will return a HTML file with successed HTTP response code. The recieved HTML file will be handled by the browser that the client is using.
```
// Steps after browser recieving HTML file from server

1. Analyzes syntax of HTML file, Parsing.
2. Creates data structure of the DOM by referring to the result of the analysis.
3. Start to render the page with given DOM structure.
4. Portrait / paint the page by referring to CSS file, matching DOM tree and the instructions on CSS. (Images get loaded after rendering DOM + CSS)
5. Apply javascript files to make the page more interactive.
```

Since browsers' main purpose is to view HTML pages, they can be called as 'remote page previewers'.

