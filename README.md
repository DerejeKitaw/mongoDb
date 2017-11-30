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