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
"band_members":[
     {
      "name": "John",
      "instrument":"guitar"
     },
     {
      "name": "Paul",
      "instrument":"bass guitar"
    },
    {
      "name": "George",
      "instrument":"guitar"
    },
    {
     "name": "Ringo",
     "instrument":"drums"
    }
 ]
```

