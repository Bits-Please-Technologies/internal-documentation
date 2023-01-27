# Pagination
If you want to limit the amount of data, you can use pagination. You can send a `pagination` object in the data parameters object to get a specified amount of data. 

## Data Parameters Object
The `pagination` object contains the following properties:

`page: int`: defines which page you want to access.
`pageSize: int`: defines the amount of items per page you want to receive

When sending an initial request, you must set the following properties to `null`:
`totalRecords` and `totalPages`.

The response will contain a header with the pagination object sent back. This is what a header response looks like: 

```json
{
  "page": 5,
  "pageSize": 10,
  "totalRecords": 101,
  "totalPages": 11,
  "hasNextPage": true
}
```

(overview of the object and explanations of the different properties)