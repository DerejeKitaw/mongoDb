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