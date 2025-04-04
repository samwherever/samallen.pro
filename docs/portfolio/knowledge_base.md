---
title: Knowledge Base
---

!!!note

    This was written as an article for non-technical users in an internal knowledge base, explaining the differences between the company's two APIs.

### API Primer
REST, or **RE**presentional **S**tate **T**ransfer, is a technology for enabling Web services to more easily interact and work with
data. Through a REST API, a program can connect to a different program via the Web in order to perform CRUD
operations - Create, Replace, Update, or Delete. The Sertifi REST API enables a client's application to connect to the
Sertifi application to access and edit booking data (signatures, participants, payments, etc).

For Sertifi, the REST and SOAP APIs serve the same purpose - enabling customers to connect to our application - but each
customer will use either SOAP or REST depending on their technical resources and requirements. The REST API is most common, as it's easier and cheaper to set up and run.

!!!tip
    
    REST is like a Ferrari - popular because it's fast, flexible, and more fun to use.

    SOAP is like an ambulance - used for very important reasons, but typically reserved only for situations where it's
    truly needed.

**REST API Advantages**

* REST APIs can send and receive data in JSON, CSV, or RSS formats, which are used by a wide variety of programming
languages, such as JavaScript, Python, Ruby, and Go.
* REST calls use common English verbs (GET, POST, PUT, DELETE) to describe their purpose, making it easier to
understand what a particular function is intended to accomplish.
* The response codes for REST are the same as HTTP response codes used across the web, which can make it easier to
understand if a call was successful or not, and why. For instance, a GET call requesting a resource that could not be
found would result in the familiar **404 NOT FOUND** error message.
* REST uses significantly less bandwidth than SOAP, making the process faster and much more efficient.
* The JSON format commonly used by REST APIs is easier to work with than the XML format used by SOAP APIs. For
example, to input data for a group of four people using XML, you'd have to write something like:

```html
<band_members>
    <member>
       <name>John</name>
       <instrument>Guitar</instrument>
    </member>
    <member>
       <name>Paul</name>
       <instrument>Bass Guitar</instrument>
    </member>
    <member>
      <name>George</name>
      <instrument>Guitar</instrument>
    </member>
    <member>
      <name>Ringo</name>
      <instrument>Drums</instrument>
    </member>
</band_members>
```

To accomplish the same thing in JSON, all you would need to write is:

```json
{
    "band_members": [
        {
            "name": "John",
            "instrument": "guitar"
        },
        {
            "name": "Paul",
            "instrument": "bass guitar"
        },
        {
            "name": "George",
            "instrument": "guitar"
        },
        {
            "name": "Ringo",
            "instrument": "drums"
        }
    ]
}
```

**HTTP Response Code Reference**

!!!tip

    This table is a general overview of what various status codes signify. The exact meaning of a status code will depend on the call’s method (GET, PUT, POST, DELETE) and what it was requesting or attempting to change. For example, a successful call using the `GET /v1/folders/{folderId}` method would return the HTTP response code 200, with a link to the folder that was requested.



|Code Number|Code Response|Definition|Notes & Fixes|
|-----------|-------------|----------|-------------|
| 200 | OK | Successful request | |
| 201| Created | Successful request. A new resource has been created. |
| 204 | N/A | The server has successfully fulfilled the request, but there is no content to send in the response. | Example: You ran a DELETE call, in which there is no data to return. The server returns the 204 code to indicate a successful operation. |
| 400 | Bad Request | The API Server is refusing the request because of one or more errors in syntax, or missing information. | Ensure the request contains no syntax errors or spelling errors, as well asconfirming that the request type (GET, POST, PUT, DELETE) contains the required parameters. |
| 401 | Unauthorized | The API server understood the request, meaning that the call was properly entered, but the server will not fulfill the request unless the user can prove they are authorized. | Ensure the customer is using the correct API access code. The 401 error code signifies that authentication is still possible, e.g. that they will eventually be able to make the call after fixing the authentication problem. |
| 403 | Forbidden | The API server understood the request, meaning that the call was properly entered, but the user is prohibited from making API calls. | |
| 409 | Conflict | There is a conflict between the resource currently available on the server and the resource that the user is attempting to upload.| This usually occurs during a PUT call as the user attempts to replace or update a file. |
| 500 | Internal Server Error | General error code | Attempt the API call once more |
| 504 | Gateway Timeout | The server “timed out”, or took too long to respond to the request. | Try the request again in a few minutes. If this error persists, ensure the infrastructure team is aware. |