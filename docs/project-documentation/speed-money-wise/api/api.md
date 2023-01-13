# Speed Money Wise API Documentation

## Introduction
For our webapplication, we are going to use a frontend built with Next JS and a backend that is built using NestJS.

## Contents
- [[filters |Filters]]
- [[sorting|Sorting]]
- [[pagination|Pagination]]

## Routes
(You can find all the API endpoints here: [[api-endpoints|API Endpoints]])

### GET
To fetch data, use a ```GET``` request on a particular route you want to fetch data from. 

### Using Data-Param request header for specific data
There are 2 ways data can be fetched: with and without header parameters.
- If you don't send a header parameter, you will recieve **all** data of the current route back. (even if there are a million records in the database!!).
- If you do specify a header parameter, you can [[filters|filter]], [[sorting|sort]] and [[pagination|paginate]] the data sent back by a route.  

### How to send data parameters
The data parameters are sent as a string-parsed object through the "`Data-Params`" custom HTTP header.

An example of what the data parameter object looks like before it has been parsed: 

```json
{
  "pagination": {
    "page": 1,
    "pageSize": 10,
    "totalRecords": null,
    "totalPages": null
  },
  "filter": {
    "status": "pending",
    "createdAt": "",
    "dateRange": {
      "field": "createdAt",
      "startDate": "2023-01-11T14:12:07.510Z",
      "endDate": "2023-01-12T14:12:07.510Z"
    },
    "sender": {
      "firstName": "John",
      "lastName": "Doe",
      "occupation": "Developeree"
    },
    "receiver": {
      "firstName": "Johnny",
      "lastName": "Moe"
    }
  },
  "sort": {
    "sortBy": "status",
    "order": "asc"
  }
}
```

Explanations for every property will be given in the corresponding sections. 
You should then parse the object as a string without any newline characters. 
Here's an example of what a string parsed data-parameters object looks like: 

```ts
"{"pagination":{"page":1,"pageSize":10,"totalRecords":null,"totalPages":null},"filter":{"status": "pending","createdAt":"","dateRange": {"field": "createdAt","startDate": "2023-01-11T14:12:07.510Z","endDate": "2023-01-12T14:12:07.510Z"},"sender":{"firstName":"John","lastName":"Doe","occupation":"Developeree"},"receiver":{"firstName":"Johnny","lastName":"Moe"}},"sort":{"sortBy":"status","order":"asc"}}"
```  
