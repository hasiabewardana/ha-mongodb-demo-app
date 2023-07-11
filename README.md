# **ha-mongodb-demo-app**
This project has all the scripts and examples of MongoDB.

## **Connect to the MongoDB instance**
```
mongodb://localhost:27017/
```

## **List all databases**
```
show dbs
```

## **Connect to a specific db**
```
user flights
```

## **Basic CRUD operations**
### Insert a document into a collection
```
db.flightData.insertOne({
    "departureAirport": "MUC",
    "arrivalAirport": "SFO",
    "aircraft": "Airbus A380",
    "distance": 12000,
    "intercontinental": true
  });
```
