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
### **Insert a document into a collection**
```
db.flightData.insertOne({
    "departureAirport": "MUC",
    "arrivalAirport": "SFO",
    "aircraft": "Airbus A380",
    "distance": 12000,
    "intercontinental": true
  });
```

### **Insert multiple documents into a collection**
```
db.flightData.insertMany([
  {
    "departureAirport": "MUC",
    "arrivalAirport": "SFO",
    "aircraft": "Airbus A380",
    "distance": 12000,
    "intercontinental": true
  },
  {
    "departureAirport": "LHR",
    "arrivalAirport": "TXL",
    "aircraft": "Airbus A320",
    "distance": 950,
    "intercontinental": false
  }
]);
```

### **Query all documents without formatting**
```
db.flightData.find();
```

### **Query all documents with formatting**
```
db.flightData.find().pretty();
```

### **Query first matching document**
```
db.flightData.findOne({departureAirport: "MUC"});
```
```
db.flightData.findOne({distance: {$gt: 10000}});
```

### **Update all documents**
```
db.flightData.updateMany({}, {$set: {distance: 11000}});
```

### **Update all documents with additional fields and/or sub-documents**
```
db.flightData.updateMany({}, {$set: {details: {pilot: "John Doe", seats: 100}}});
```

### **Update all documents with additional data of array**
```
db.flightData.updateMany({}, {$set: {transits: ["Duabai", "Montrial"]}});
```

### **Update first matching document with additional fields and/or sub-documents**
```
db.flightData.updateOne({departureAirport: "MUC"}, {$set: {details: {pilot: "James Smith", seats: 110}}});
```

### **Update first matching document with additional data of array**
```
db.flightData.updateOne({transits: "Duabai"}, {$set: {transits: ["London", "Montrial"]}});
```

### **Delete first matching document***
```
db.flightData.deleteOne({departureAirport: "MUC"});
```

### **Delete all documents**
```
db.flightData.deleteMany({});
```
