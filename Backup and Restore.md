# Show all databases
    > show dbs
    admin             0.000GB
    angularexpress    0.000GB
    angularfullstack  0.000GB
    local             0.000GB
    school            0.000GB
    > 

# Backup all databases - need to have admin access
    mongodump  -- command will create dump folder and backup all database

# Delete all data base 
    use admin
    db.dropDatabase()
    ....etc

# Restore database
    mongorestore

# Backup only school database

    mongodump --db school

# Restore school - need to give path of the data base. dump/school: is the location

    mongorestore --db school dump/school

# How to backup a collection

    > use school
    switched to db school
    > show collections
    students
    > ---------------How do we backup students collection only
    mongodump --db school --collection students

# Restore student collections
    db.students.drop()
    mongorestore --db school --collection students dump/school/student.bson

