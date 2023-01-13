# Filtering

If you want to get specific data from a table, you can send a `filter` object in the data params object. (Every time "data params/parameters object" is mentioned from here on out, it is refering to the object that is sent throught the data params header.) 

## Data Parameters Object
The `filter` object can contain the following properties:

*fieldName*: `string` , matches the string by default
Example: 
```json
"filter": {
    "firstName": "John",
    "lastName": "Doe"
  }
```

*fieldName*: `number` , selects the specific number by default
Example: 
```json
"filter": {
    "amount": 1000,
    "fee": 10
  }
```

If you want more control over the filter, you can specify a filter mode as well. These modes are prisma filter conditions. You can find the prisma filter conditions here: [Prisma filter conditions](https://www.prisma.io/docs/reference/api-reference/prisma-client-reference#scalar-list-filters)

Example: (this returns all records with an amount greater than 0.5)
```json 
"filter": {
    "amount": {
	    "mode": "gte",
		"value": "0.5"
    }
  }
```

### Filtering when there's a nested object

If you want to get data from a field which has a relationship with another table (such as a client's firstname), or when there is a nested object, you can send an object instead.
This object contains the different fields that you want to filter. 

Example: 
This code gets all transactions where the sender's first name is "John" and the last name is "Doe".

```json
"filter": {
    "sender": {
      "firstName": "John",
      "lastName": "Doe",
  }
```

You can also specify different modes on every child object. 

### Filtering with dates

There are 2 ways to filter dates:

- By sending just a field and specific date
- By defining a dataRange object.

Sending a date field with a date parsed as an ISO date, the api will return a specific date.
Example: 
```json
"filter": {
    "createdAt": "2023-01-10T14:12:07.510Z"
}
```

You can also search between two dates.
Example: 
```json
"filter": {
    "dateRange": {
      "field": "createdAt",
      "startDate": "2023-01-10T14:12:07.510Z",
      "endDate": "2023-01-11T14:12:07.510Z"
    }
  }
```

Adding a date field, but not giving it a value will default it to the current day.