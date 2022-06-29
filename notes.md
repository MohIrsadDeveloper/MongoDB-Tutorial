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
                                db.createCollection("testCollection", {capped : true, max : 4});
                 <!-- Create Collection and insert document -->
            2. db.<database_name>.insert(<document>);
                Eg. =>
                    1.db.myCollectionName.insert({name : "mongodb"});

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
    