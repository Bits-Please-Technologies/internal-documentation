# Sorting
If you want to sort the requested data by a specific field, you can send a `sort` object in the data params object. You can also change the sort order (ascending and descending order).

## Data Parameter Object
The `sort` object contains the following properties: 
`sortBy`: 
This can be either a `string` with the *fieldName* or, if it's a nested object, an object with the *fieldName* as prop name.

`order`: 
This can be `ascending` or `descending`.

Example 1: (This returns a list of clients where they are sorted by first name, from Z-A (Descending))
```json
"sort": {
    "sortBy": "firstName",
    "order": "desc"
  }
```

Example 2: (This returns a list of transactions where it is sorted by sender's first names, from A-Z (ascending))
```json
"sort": {
    "sortBy": {
      "sender": "firstName"
    },
	"order": "asc"
}
```

