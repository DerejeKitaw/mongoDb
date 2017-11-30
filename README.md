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
    use my_db
    db.users.insert({ "name": "Dereje", "email": "dereje.kitaw@gmail.com"})
    db.users.find()
    db.users.find().pretty()
    db.users.find({"name": "dereje"}).pretty()