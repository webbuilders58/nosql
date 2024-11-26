# nosql
Ref mongodb connection: https://www.mongodb.com/docs/drivers/java/sync/v5.1/fundamentals/connection/connect/

ref javatpoint: https://www.javatpoint.com/java-mongodb

java code
```java
package com.mycompany.mavenproject1;
import com.mongodb.*;
import com.mongodb.client.FindIterable;
import org.bson.Document;

import com.mongodb.client.MongoClient;
import com.mongodb.client.MongoClients;
import com.mongodb.client.MongoCollection;
import com.mongodb.client.MongoDatabase;

public class NewClass {
    public static void main(String[] args) {
        String uri = "mongodb://localhost:27017";

        ServerApi serverApi = ServerApi.builder()
                .version(ServerApiVersion.V1)
                .build();

        MongoClientSettings settings = MongoClientSettings.builder()
                .applyConnectionString(new ConnectionString(uri))
                .serverApi(serverApi)
                .build();

        try (MongoClient mongoClient = MongoClients.create(settings)) {
            MongoDatabase database = mongoClient.getDatabase("test");
            try {
    
                MongoCollection<Document> collection = database.getCollection("persons");
                //INSERT
//        Document document = new Document("title", "MongoDB")
//                .append("description", "Database")
//                .append("likes", 100)
//                .append("url", "http://www.mongodb.com")
//                .append("by", "User");
//        collection.insertOne(document);


//UPDATE
//       Document document = new Document("title", "MongoDB");
//               
//        collection.updateOne(document,new Document("$set",new Document("title","anudeep")));

             

//DELETE
//        collection.deleteOne(new Document("title","MongoDB"));


//FIND
//   FindIterable<Document> d = collection.find(new Document("by","User"));
//                for(Document doc: d){
//                    System.out.println(doc.toJson());
//
//                }

                System.out.println("Pinged your deployment. You successfully connected to MongoDB!");
            } catch (MongoException me) {
                System.err.println(me);
            }
        }
    }
}

```
