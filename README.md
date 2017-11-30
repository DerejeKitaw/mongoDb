# mongoDb

    MongoDb is a Open Source database and used to store data for very high performance applications.

    collection is like a table 
    Document is like a row
    Field is like a column

    Collection is schema-less

# 2_Install mongoDB from [mongoDB](https://www.mongodb.com/)

    move dowenloaded mongodb file to Applications

# 3_Registor mongo path

    cd ~ change directory to home
    code . open the folder and update .bash_profile
    PATH="/Application/mongodb/bin:${PATH}"
    export PATH
    restart terminal and mongod --version to check mongo version

    for window set enviromental variable in advanced option

# 3_Run mongoDB

    mongod for window mongod.exe in the mongodb instalation folder

    mongod will look for date file data/db

    if data/db folder available mongo will wait for for connection on port 27017

    to change mongo port:
        mongod --port 27018
    to open mongo in another terminal
        mongo --port 27018

# 4_Play with mongo once mongo works on the terminal
    [Doc](https://docs.mongodb.com/manual/crud/)
    
# 5_Show all databases

    show dbs
    > show dbs
    admin             0.000GB
    angularexpress    0.000GB
    angularfullstack  0.000GB
    local             0.000GB

# 6_use angularexpress database

    > use angularexpress
    switched to db angularexpress
    
# 7_list all collections in angularexpress database

    > show collections
    counties
    inverters
    panels
    users
    
# 8_What is inside collection counties?

    > db.counties.find().pretty()
    {
        "_id" : ObjectId("59d712690aadb80c5d94dc65"),
        "countyName" : "Baltimore",
        "groundSnowLoad" : 25,
        "rapidShutdown" : true,
        "windSpeed" : 115,
        "__v" : 0
    }
    {
        "_id" : ObjectId("59d7132a0aadb80c5d94dc66"),
        "countyName" : "Montgomery",
        "groundSnowLoad" : 25,
        "rapidShutdown" : true,
        "windSpeed" : 115,
        "__v" : 0
    }
    {
        "_id" : ObjectId("59e19cc7ddab505381b056ce"),
        "countyName" : "PG",
        "groundSnowLoad" : 300,
        "rapidShutdown" : true,
        "windSpeed" : 12,
        "__v" : 0
    }

# 9_Select PG counties

    > db.counties.find({"countyName": "PG"}).pretty()
    {
        "_id" : ObjectId("59e19cc7ddab505381b056ce"),
        "countyName" : "PG",
        "groundSnowLoad" : 300,
        "rapidShutdown" : true,
        "windSpeed" : 12,
        "__v" : 0
    }

# 10_Check current working database

    > db
    angularexpress

# 11_Create new database mydb

    > use mydb          --this will create mydb database if doesnt exist. 
                          If exist it will switch to mydb
    switched to db mydb

    > db                --will list current working database
    mydb

    > show dbs          --mydb databsae is not listed because it do not have data
    admin             0.000GB
    angularexpress    0.000GB
    angularfullstack  0.000GB
    local             0.000GB

# 12_Insert data

    > db.mycollection.insert({"name":"Dereje"})
    WriteResult({ "nInserted" : 1 })

    > show dbs
    admin             0.000GB
    angularexpress    0.000GB
    angularfullstack  0.000GB
    local             0.000GB
    mydb              0.000GB

# 13_delete current database mydb

    > db.dropDatabase()
    { "dropped" : "mydb", "ok" : 1 }

    > show dbs
    admin             0.000GB
    angularexpress    0.000GB
    angularfullstack  0.000GB
    local             0.000GB

# 14_Create mydb database and create myCollection

    > use mydb
        switched to db mydb

    > db.createCollection("myCollection")           --one way to create a collection
        { "ok" : 1 }

    > show collections
        myCollection
        
    > db.myCollection2.insert({"name":"Dereje"})    --Another way to create a collection
        WriteResult({ "nInserted" : 1 })
    > show collections
        myCollection
        myCollection2

# 15_Drop a collection

    > db.mycollection.drop()    --is case sensitive
        false
    > db.mycollections.drop()
        false
    > show collections
        myCollection
        myCollection2
    > db.myCollection
        mydb.myCollection
    > db.myCollection.drop()
        true
    > db.myCollection2.drop()
     true

# 16_Insert one document in a database

    > use school
    switched to db school

    > db.students.insert({ "StudentNo": "1", "FirstName" :"Dereje","LastName": "Kitaw","Age":"35"})
    WriteResult({ "nInserted" : 1 })

# 17_Insert multipe document

    > db.students.insert([{         "StudentNo": "1",         "FirstName": "Dereje",         "LastName": "Kitaw",         "Age": "35"     },     {         "StudentNo": "2",         "FirstName": "Aman",         "LastName": "Abdisa",         "Age": "30"     },     {         "StudentNo": "3",         "FirstName": "Alex",         "LastName": "Yemam",         "Age": "40"     }])

    BulkWriteResult({
	"writeErrors" : [ ],
	"writeConcernErrors" : [ ],
	"nInserted" : 3,
	"nUpserted" : 0,
	"nMatched" : 0,
	"nModified" : 0,
	"nRemoved" : 0,
	"upserted" : [ ]
    })

    > db.students.find().pretty()

    {
        "_id" : ObjectId("5a1f96adde48cb60870862f8"),
        "StudentNo" : "1",
        "FirstName" : "Dereje",
        "LastName" : "Kitaw",
        "Age" : "35"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f9"),
        "StudentNo" : "2",
        "FirstName" : "Aman",
        "LastName" : "Abdisa",
        "Age" : "30"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862fa"),
        "StudentNo" : "3",
        "FirstName" : "Alex",
        "LastName" : "Yemam",
        "Age" : "40"
    }
# 18_Select the first entry

    > db.students.findOne()
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f8"),
        "StudentNo" : "1",
        "FirstName" : "Dereje",
        "LastName" : "Kitaw",
        "Age" : "35"
    }
    > 

# 19_Find student number 2

    > db.students.find({"StudentNo":"2"}).pretty()
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f9"),
        "StudentNo" : "2",
        "FirstName" : "Aman",
        "LastName" : "Abdisa",
        "Age" : "30"
    }
    > 
# 20_Find all student whose age is greater than 31

    > db.students.find({"Age":{$gt :"31"}}).pretty()
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f8"),
        "StudentNo" : "1",
        "FirstName" : "Dereje",
        "LastName" : "Kitaw",
        "Age" : "35"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862fa"),
        "StudentNo" : "3",
        "FirstName" : "Alex",
        "LastName" : "Yemam",
        "Age" : "40"
    }
    > 

    $gt --greter than
    $gte --greter than or equal to
    $ls --less than or equal to
    $lse --less than or equal to
    $ne --not equal to

# 21_and use comma

    Search student first name Dereje and age 35
    > db.students.find({"FirstName":"Dereje","Age":"35"}).pretty()
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f8"),
        "StudentNo" : "1",
        "FirstName" : "Dereje",
        "LastName" : "Kitaw",
        "Age" : "35"
    }
    > 
# 22_or ({$or : [{},{},{}]})

    > db.students.find({$or :[{"FirstName":"Dereje"},{"Age":"34"}]}).pretty()
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f8"),
        "StudentNo" : "1",
        "FirstName" : "Dereje",
        "LastName" : "Kitaw",
        "Age" : "35"
    }
    > 
# 23_and or ({$or : [{},{},{}]})  --firstName Dereje or Age 20 or 35

    > db.students.find({"FirstName":"Dereje", $or :[{"Age":"20"},{"Age":"35"}]}).pretty()
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f8"),
        "StudentNo" : "1",
        "FirstName" : "Dereje",
        "LastName" : "Kitaw",
        "Age" : "35"
    }
    > 

# 24_Update student with _id=5a1f96adde48cb60870862f8 to last name to Codder
    
    > db.students.update(
        {
            "_id": ObjectId("5a1f96adde48cb60870862f8")
        },
        {
            $set : {"LastName" : "Codder"}
        }
    )
    WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

    > db.students.find().pretty()
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f8"),
        "StudentNo" : "1",
        "FirstName" : "Dereje",
        "LastName" : "Codder",
        "Age" : "35"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f9"),
        "StudentNo" : "2",
        "FirstName" : "Aman",
        "LastName" : "Abdisa",
        "Age" : "30"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862fa"),
        "StudentNo" : "3",
        "FirstName" : "Alex",
        "LastName" : "Yemam",
        "Age" : "40"
    }
    > 

# 25_Update multiple row

    > db.students.update(
        {
            "Age": "30"
        },
        {
            $set : {"LastName" : "Young"}
        },
        {
            multi : true
        }
    )

    WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
    db.students.find().pretty()
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f8"),
        "StudentNo" : "1",
        "FirstName" : "Dereje",
        "LastName" : "Codder",
        "Age" : "35"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f9"),
        "StudentNo" : "2",
        "FirstName" : "Aman",
        "LastName" : "Young",
        "Age" : "30"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862fa"),
        "StudentNo" : "3",
        "FirstName" : "Alex",
        "LastName" : "Yemam",
        "Age" : "40"
    }
    > 

# 26_update existing data using save. Save used to insert and update existing data

    > db.students.save(
        {
        "_id" : ObjectId("5a1f96adde48cb60870862f8"),
        "StudentNo" : "1",
        "FirstName" : "Dereje",
        "LastName" : "Tesfaye",
        "Age" : "30"
    }
    )

    WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
    db.students.find().pretty()
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f8"),
        "StudentNo" : "1",
        "FirstName" : "Dereje",
        "LastName" : "Tesfaye",
        "Age" : "30"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f9"),
        "StudentNo" : "2",
        "FirstName" : "Aman",
        "LastName" : "Young",
        "Age" : "30"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862fa"),
        "StudentNo" : "3",
        "FirstName" : "Alex",
        "LastName" : "Yemam",
        "Age" : "40"
    }
    > 

# 27_Create new data using save. Save used to insert and update existing data
     > db.students.save(
        {
        "_id" : ObjectId("5a1f96adde48cb60870862fd"),
        "StudentNo" : "5",
        "FirstName" : "Winta",
        "LastName" : "Tesfaye",
        "Age" : "30"
    }
    )
    WriteResult({
        "nMatched" : 0,
        "nUpserted" : 1,
        "nModified" : 0,
        "_id" : ObjectId("5a1f96adde48cb60870862fd")
    })

    > db.students.find().pretty()

    {
        "_id" : ObjectId("5a1f96adde48cb60870862f8"),
        "StudentNo" : "1",
        "FirstName" : "Dereje",
        "LastName" : "Tesfaye",
        "Age" : "30"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f9"),
        "StudentNo" : "2",
        "FirstName" : "Aman",
        "LastName" : "Young",
        "Age" : "30"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862fa"),
        "StudentNo" : "3",
        "FirstName" : "Alex",
        "LastName" : "Yemam",
        "Age" : "40"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862fd"),
        "StudentNo" : "5",
        "FirstName" : "Winta",
        "LastName" : "Tesfaye",
        "Age" : "30"
    }
    > 

# 27_Delete document. Warning db.students.remove() will remove all data

    > db.students.remove(
        {
        "_id" : ObjectId("5a1f96adde48cb60870862fd"),
    }
    )

    WriteResult({ "nRemoved" : 1 })
    > db.students.find().pretty()
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f8"),
        "StudentNo" : "1",
        "FirstName" : "Dereje",
        "LastName" : "Tesfaye",
        "Age" : "30"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862f9"),
        "StudentNo" : "2",
        "FirstName" : "Aman",
        "LastName" : "Young",
        "Age" : "30"
    }
    {
        "_id" : ObjectId("5a1f96adde48cb60870862fa"),
        "StudentNo" : "3",
        "FirstName" : "Alex",
        "LastName" : "Yemam",
        "Age" : "40"
    }
    > 



# 28_Delete one document. Warning db.students.remove() will remove all data
    --1 will restrict to delete only one document   
      even though multiple student with age 30
    > db.students.remove(
        {
        "Age" : "30",
        },1                         
        )
        WriteResult({ "nRemoved" : 1 })

        > db.students.find().pretty()

        {
            "_id" : ObjectId("5a1f96adde48cb60870862f9"),
            "StudentNo" : "2",
            "FirstName" : "Aman",
            "LastName" : "Young",
            "Age" : "30"
        }
        {
            "_id" : ObjectId("5a1f96adde48cb60870862fa"),
            "StudentNo" : "3",
            "FirstName" : "Alex",
            "LastName" : "Yemam",
            "Age" : "40"
        }
        > 
# 29_Projection - Means selecting only necessary data rather than selecting whole of the data of a document >db.COLLECTION_NAME.find({},{KEY:1})

    db.students.find(
        {},
        {"FirstName" :1}
    )

    { "_id" : ObjectId("5a1f96adde48cb60870862f9"), "FirstName" : "Aman" }
    { "_id" : ObjectId("5a1f96adde48cb60870862fa"), "FirstName" : "Alex" }
    > 

    Always _id will be display

    ## remove _id

    db.students.find(
        {},
        {"FirstName" :1 , "_id" : 0}
    )

    { "FirstName" : "Aman" }
    { "FirstName" : "Alex" }
    > 

# 30_Sort , Skip, and Limit

    db.students.find(
        {},
        {"StudentNo" :1 , "FirstName" : 1, "_id" :0}
    )

    { "StudentNo" : "2", "FirstName" : "Aman" }
    { "StudentNo" : "3", "FirstName" : "Alex" }
    > 

    ## limit output only one
        db.students.find(
            {},
            {"StudentNo" :1 , "FirstName" : 1, "_id" :0}
        ).limit(1)

        { "StudentNo" : "2", "FirstName" : "Aman" }
        > 
    ## Skip first data
        db.students.find(
            {},
            {"StudentNo" :1 , "FirstName" : 1, "_id" :0}
        ).skip(1)

        { "StudentNo" : "3", "FirstName" : "Alex" }
        > 

    ## skip the first result and show the next three result

        db.students.find(
            {},
            {"StudentNo" :1 , "FirstName" : 1, "_id" :0}
        ).skip(1).limit(3)

        { "StudentNo" : "3", "FirstName" : "Alex" }
        > 
    ## sort Acending by first name

        db.students.find(
            {},
            {"StudentNo" :1 , "FirstName" : 1, "_id" :0}
        ).sort({"FirstName" : 1})

        { "StudentNo" : "3", "FirstName" : "Alex" }
        { "StudentNo" : "2", "FirstName" : "Aman" }
        > 

    ## Sort Decending

        db.students.find(
            {},
            {"StudentNo" :1 , "FirstName" : 1, "_id" :0}
        ).sort({"FirstName" : -1})

        { "StudentNo" : "2", "FirstName" : "Aman" }
        { "StudentNo" : "3", "FirstName" : "Alex" }
        > 
# 31_Indexing - Create index for uniq field

    ## To see the use of index create 10,000,000 students

    use temp
    for(i=0; i <10000000; i++){
        db.posts.insert({"student_id" : i, "name" : "mark});
    }

    ## To see data
    db.posts.find()

    ## Find student_id=1000 and see how long it takes befor indexing
    db.posts.find({"student_id":1000});

    ## Adding index
    db.posts.ensureIndex({"student_id" :1);

    ## Find student_id=1000 and see how long it takes after indexing
    db.posts.find({"student_id":1000});

    ## removing index
    db.posts.dropIndex("student_id" :1);

# 32_Aggregation - groups multiple elements from different db

    

