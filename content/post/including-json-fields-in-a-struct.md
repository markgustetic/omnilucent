+++
date = "2016-09-27T13:49:29-04:00"
tags = []
title = "Including JSON Fields in a Go Struct"
share = true
summary = "test"
+++

Marshalling a structure with a JSON field in it.

This is useful for APIs that need to send back JSON within their JSON responses that contain other information along with the JSON.

### Give example of what output look likes (double encoded)

### Create a struct to hold the JSON string

```Go
type JSONString struct {
   JSONField string
}
```

### Write the MarshalJSON function
```Go
 func (j JSONString) MarshalJSON() ([]byte, error) {
   return []byte(j.JSONField), nil
 }
```

### Explain MarshalJSON Interface


### Example usage

```Go
 func ExportJSON() (string, error) {
   sampleJSON := `{ "test": "test" }`

   dataSummary := DataSummary{Data: JSONString{JSONField: sampleJSON}}

   dataSummaryJSON, err := json.Marshal(dataSummary)

   if err != nil {
     return "", err
   }

   return string(dataSummaryJSON), nil
 }
```

### Full example