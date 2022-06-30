<!-- With a brief introduction tour to MongoDB, let us dive into working with MongoDB. -->

<!-- Check MongoDB version -->
db.version()    

1. Getting started with MongoDB =>
        1. Install MongoDB on Ubuntu
        2. Mongo Shell
        3. MongoDB Script

2. MongoDB Database => 
        1. MongoDB Database
        2. MongoDB Create Database
        3. MongoDB Delete Database

3. MongoDB Collection =>
        1. MongoDB Collection
        2. MongoDb Create Collection
        3. MongoDB Delete Collection

4. MongoDB Document => 
        1. MongoDB Document
        2. MongoDB Insert Document
        3. MongoDB Query Documents
        4. MongoDB Update Document
        5. MongoDB Delete Document
        6. MongoDB Limit Documents
        7. MongoDB Skip Documents
        8. MongoDB Sort Documents
        9. MongoDb Setup Replica Set

5. MongoDB Concepts =>
        1. MongoDB Text Search
        2. MongoDb MapReduce
        3. MongoDB Backup



<!-- **************** -->
<!-- Create Database -->
1. MongoDB Database =>
    1. Create Database => use <database_name>
        ex --> use tutorialkart

    2. Show Database => show dbs;
        ex --> show dbs

    3. Use Database => use <database_name>;
        ex. --> use tutorialkart

    4. Delete Database => db.dropDatabase();
        Steps -->   1. go to particular database ==> use tutorialkart
                    2. delete or drop the database ==> db.dropDatabase()

    5. Know Currently selected Database => db;
        ex --> db

<!-- Create Collections -->
2. MongoDB Collection =>
    1. Create Collection =>
            <!-- only create collection -->
        1. db.createCollection(<collection_name>);
            Steps =>
                1. Goto Database ==> use tutorialkart
                2. create Collection ==> db.createCollection("collectionName")
                    Eg. =>
                        1. db.createCollection("myCollectionName");
                        2. db.createCollection("myCollectionName", {capped : boolean, size : Size of Collection in Bytes, max : Number of MongoDb Documents that could be stored in the collection, only Integer })
                            ex. -->
                                db.createCollection("Users", {capped : true, max : 4});
                 <!-- Create Collection and insert document -->
            2. db.<database_name>.insert(<document>);
                Eg. =>
                    1.db.Users.insert({name : "mongodb"});

    2. Show Collection => show collections;
        Steps =>
            1. use DatabaseName
            2. show collections

    3. Delete Collection => db.<collectionName>.drop();
        Steps =>
            1. use DatabaseName
            2. db.collectionName.drop();


<!-- MongoDB Document - Structure and Sample Documents -->
3. MongoDB Document => 
    <!-- Create Document -->
    Create Document =>
        1. db.<collectionName>.insertOne(<document>);
            ex. ==>
                db.Users.insert({name : "abdul"})
        2.db.<collectionName>.insertMany([<document>]);
            ex. ==>
                db.Users.insertMany([{name : "asma"}, {name : "aiysha"}])

    Steps ==>
        1. use tutorialkart
        2. db.Users.insertOne(<document>)

    <!-- Show Document -->
    Show Documents =>
        1. db.<collectionName>.find();
           db.<collectionName>.find({});
            ex. ==>
                db.Users.find();
        2.db.<collectionName>.find().pretty(); <!-- It shows is prettier format or readable format. -->
            ex. ==>
                db.Users.find().pretty();
        <!-- Show as Coditional Criteria -->
        3. db.<collectionName>.find({<criteria>})
            ex. ==>
                db.Users.find({name: "abdul"});
                    <!-- or -->
        3. db.<collectionName>.find(criteria);
            ex. ==>
                criteria = {name : "asma"}
                db.Users.find(criteria);
        <!-- find based on projection -->
        4. Projection mean find the documents and show only particular fields, if we want that field give projection_value as 1 otherwise to hide give projection_value as 0.
            ex. ==>
                db.Users.find({}, {name : 1, _id : 0})

    <!-- Delete Document -->

    <!-- Update Document -->
    Delete Document =>
        1. db.<collectionName>.update(<criteria>, <update>, <options>);
            ex. =>
                db.Users.update({name: "abdul"}, {name : "abdul", email : "abdul@gmail.com, age : 16})
        2.db.<collectionName>.update(<criteria>, <$set:<update>>, <multi : true>)
            ex. =>
                db.Users.update({location : "mumbai"}, {$set: {bonus : 250}}) <!-- for single update -->
                db.Users.update({location : "mumbai"}, {$set: {bonus : 250}}, {multi : true}) <!-- for multi update -->