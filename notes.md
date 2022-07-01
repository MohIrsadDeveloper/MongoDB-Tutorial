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
    1. Create Document =>
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
    2. Show Documents =>
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


    <!-- Update Document -->
    3. Update Document =>
        1. db.<collectionName>.update(<criteria>, <update>, <options>);
            ex. =>
                db.Users.update({name: "abdul"}, {name : "abdul", email : "abdul@gmail.com, age : 16})
        2.db.<collectionName>.update(<criteria>, <$set:<update>>, <multi : true>)
            ex. =>
                db.Users.update({location : "mumbai"}, {$set: {bonus : 250}}) <!-- for single update -->
                db.Users.update({location : "mumbai"}, {$set: {bonus : 250}}, {multi : true}) <!-- for multi update -->


    <!-- Delete Document -->
    4. Delete Document =>
        <!-- To delete all documents -->
        1. db.<collectionName>.remove();
                <!-- or -->
           db.<collectionName>.remove({});
            ex. =>
                db.Users.remove() or db.Users.remove({});

        <!-- To delete on certain criteria -->
        2. db.<collectionName>.remove(<criteria>); <!-- remove all based on criteria -->
            ex. =>
                db.Users.remove({location : "mumbai"});

        2. db.<collectionName>.remove(<criteria>, JUST_ONE); <!-- delete one based on criteria -->
            ex. =>
                db.Users.remove({location : "mumbai"}, 1);

    
    <!-- Limit Documents -->
    5. Limit Document =>
        <!-- Fetch all document  -->
        1. db.<collectionName>.find().limit()
            ex. =>
                db.Users.find().limit();

        <!-- Fetch certain limit document -->
        2. db.<collectionName>.find().limit(N)
            ex. =>
                db.Users.find().limit(2);

    <!-- Skip Documents -->
    6. Skip Documents =>
        <!-- Fetch all document zero skip -->
        1. db.<collectionName>.find().skip();
            ex. =>
                db.Users.find().skip();

        <!-- Fetch with skip number -->
        2. db.<collectionName>.find().skip(2);
            ex. =>
                db.Users.find().skip(2);

        <!-- Fetch with skip and limit number -->
        3.db.<collectionName>.find().skip(2).limit(2);
            ex. =>
                db.Users.find().skip(2).limit(2);

    7. Sort Document => Sort method take 1 or -1,
                        1 is for ascending or incresing order
                        -1 is for descending or decresing order
        <!-- Sort with out any condition -->
        1. db.<collectionName>.find().sort();
            ex. =>
                db.Users.find().sort();

        <!-- Sort with one field -->
        2. db.<collectionName>.find().sort({age : 1}) <!-- for ascending order -->
           db.<collectionName>.find().sort({age : -1}) <!-- for descending order -->

        <!-- Sort with more then one field -->
        3. db.<collectionName>.find().sort({age : 1, name : 1});
           db.<collectionName>.find().sort({age : 1, name : -1});

4. MongoDB Aggregation Pipeline =>
    