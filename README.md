# Apollo Connector for TrimbleMaps REST API

This is an Apollo Connector that works with the TrimbleMaps API.
https://developer.trimblemaps.com/restful-apis/developer-guide/introduction/

## Query by address


```
query ByAddress($address: String!, $city: String!, $state: String!) {
  ByAddress(address: $address, city: $city, state: $state) {
    Lat
    Lon
  }
}
```

Pass address, city and state as strings.
Works with North America addresses only

Example:
`1600 Pennsylvania Avenue NW, Washington, DC`

Returns:
```
{
  "data": {
    "ByAddress": {
      "Lat": "38.897675",
      "Lon": "-77.036547"
    }
  }
}
```

## Query By Lat/Long coordinates

```
query ByGeo($lat: String!, $long: String!) {
  ByGeo(lat: $lat, long: $long) {
    Address
    Timezone
  }
}
```

Pass Lat, long as strings
Works worldwide and returns Address and Timezone

Example:
`48.8584° N, 2.2945° E is the Eiffel Tower`

Returns:
{
  "data": {
    "ByGeo": {
      "Address": "2 Avenue Gustave Eiffel, 75007 Paris, Île-de-France, FR, Paris",
      "Timezone": "GMT+1:00"
    }
  }
}


