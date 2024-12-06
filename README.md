# Apollo Connector for TrimbleMaps REST API

## Usage

Pass address, city and state as strings.
Works with North America addresses only

```
query ByAddress($address: String!, $city: String!, $state: String!) {
  ByAddress(address: $address, city: $city, state: $state) {
    Lat
    Lon
  }
}
```

Pass Lat, long as strings
Works worldwide and returns Address and Timezone

```
query ByGeo($lat: String!, $long: String!) {
  ByGeo(lat: $lat, long: $long) {
    Address
    Timezone
  }
}
```