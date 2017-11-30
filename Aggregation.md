# create school database

   > use school
    switched to db school

# add data with students collection

    db.students.insert(
        [
            {
                "_id": "5a1fac9d7c91cdc4e055906b",
                "id": 0,
                "StudentNo": 0,
                "FirstName": "Virginia",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 27,
                "gender": "female"
            },
            {
                "_id": "5a1fac9dceff444aae08b9ac",
                "id": 1,
                "StudentNo": 1,
                "FirstName": "Matilda",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 24,
                "gender": "female"
            },
            {
                "_id": "5a1fac9dd015e1c2907d9758",
                "id": 2,
                "StudentNo": 2,
                "FirstName": "Strong",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 29,
                "gender": "male"
            },
            {
                "_id": "5a1fac9d1fc8b2761bad88ae",
                "id": 3,
                "StudentNo": 3,
                "FirstName": "Alexandra",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 34,
                "gender": "female"
            },
            {
                "_id": "5a1fac9de0507e5ef0203089",
                "id": 4,
                "StudentNo": 4,
                "FirstName": "Everett",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 39,
                "gender": "male"
            },
            {
                "_id": "5a1fac9d54212c3d906961eb",
                "id": 5,
                "StudentNo": 5,
                "FirstName": "Hannah",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 23,
                "gender": "female"
            },
            {
                "_id": "5a1fac9d5d71cc55db09f62c",
                "id": 6,
                "StudentNo": 6,
                "FirstName": "Gwendolyn",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 21,
                "gender": "female"
            },
            {
                "_id": "5a1fac9d2b5cbacfb54b51c3",
                "id": 7,
                "StudentNo": 7,
                "FirstName": "Cross",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 32,
                "gender": "male"
            },
            {
                "_id": "5a1fac9db9bd483d7d15afea",
                "id": 8,
                "StudentNo": 8,
                "FirstName": "Antoinette",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 38,
                "gender": "female"
            },
            {
                "_id": "5a1fac9d4f5c079e922b20c7",
                "id": 9,
                "StudentNo": 9,
                "FirstName": "Ferrell",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 38,
                "gender": "male"
            },
            {
                "_id": "5a1fac9d4d8a89670f6fcea4",
                "id": 10,
                "StudentNo": 10,
                "FirstName": "Laverne",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 26,
                "gender": "female"
            },
            {
                "_id": "5a1fac9dc6cf9262fcd8d346",
                "id": 11,
                "StudentNo": 11,
                "FirstName": "Kerry",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 33,
                "gender": "female"
            },
            {
                "_id": "5a1fac9d7122a358cb8ceae2",
                "id": 12,
                "StudentNo": 12,
                "FirstName": "Graham",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 24,
                "gender": "male"
            },
            {
                "_id": "5a1fac9d4dc7f70eb92f1da0",
                "id": 13,
                "StudentNo": 13,
                "FirstName": "Carroll",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 30,
                "gender": "male"
            },
            {
                "_id": "5a1fac9df77cbef9874b4bf1",
                "id": 14,
                "StudentNo": 14,
                "FirstName": "Esperanza",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 21,
                "gender": "female"
            },
            {
                "_id": "5a1fac9df2784b0f5fbf602f",
                "id": 15,
                "StudentNo": 15,
                "FirstName": "Britt",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 22,
                "gender": "male"
            },
            {
                "_id": "5a1fac9df25fb52e6e352332",
                "id": 16,
                "StudentNo": 16,
                "FirstName": "Howell",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 37,
                "gender": "male"
            },
            {
                "_id": "5a1fac9dc5c071813e05ca59",
                "id": 17,
                "StudentNo": 17,
                "FirstName": "Josefina",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 35,
                "gender": "female"
            },
            {
                "_id": "5a1fac9d1770a92607129bb3",
                "id": 18,
                "StudentNo": 18,
                "FirstName": "Gilbert",
                "LastName": "<ReferenceError: flastName is not defined>",
                "age": 31,
                "gender": "male"
            }
            ]
    )

    BulkWriteResult({
	"writeErrors" : [ ],
	"writeConcernErrors" : [ ],
	"nInserted" : 19,
	"nUpserted" : 0,
	"nMatched" : 0,
	"nModified" : 0,
	"nRemoved" : 0,
	"upserted" : [ ]
    })
    > 

# List all students
    > db.students.find().pretty()
        {
            "_id" : "5a1fac9d7c91cdc4e055906b",
            "id" : 0,
            "StudentNo" : 0,
            "FirstName" : "Virginia",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 27,
            "gender" : "female"
        }
        {
            "_id" : "5a1fac9dceff444aae08b9ac",
            "id" : 1,
            "StudentNo" : 1,
            "FirstName" : "Matilda",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 24,
            "gender" : "female"
        }
        {
            "_id" : "5a1fac9dd015e1c2907d9758",
            "id" : 2,
            "StudentNo" : 2,
            "FirstName" : "Strong",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 29,
            "gender" : "male"
        }
        {
            "_id" : "5a1fac9d1fc8b2761bad88ae",
            "id" : 3,
            "StudentNo" : 3,
            "FirstName" : "Alexandra",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 34,
            "gender" : "female"
        }
        {
            "_id" : "5a1fac9de0507e5ef0203089",
            "id" : 4,
            "StudentNo" : 4,
            "FirstName" : "Everett",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 39,
            "gender" : "male"
        }
        {
            "_id" : "5a1fac9d54212c3d906961eb",
            "id" : 5,
            "StudentNo" : 5,
            "FirstName" : "Hannah",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 23,
            "gender" : "female"
        }
        {
            "_id" : "5a1fac9d5d71cc55db09f62c",
            "id" : 6,
            "StudentNo" : 6,
            "FirstName" : "Gwendolyn",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 21,
            "gender" : "female"
        }
        {
            "_id" : "5a1fac9d2b5cbacfb54b51c3",
            "id" : 7,
            "StudentNo" : 7,
            "FirstName" : "Cross",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 32,
            "gender" : "male"
        }
        {
            "_id" : "5a1fac9db9bd483d7d15afea",
            "id" : 8,
            "StudentNo" : 8,
            "FirstName" : "Antoinette",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 38,
            "gender" : "female"
        }
        {
            "_id" : "5a1fac9d4f5c079e922b20c7",
            "id" : 9,
            "StudentNo" : 9,
            "FirstName" : "Ferrell",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 38,
            "gender" : "male"
        }
        {
            "_id" : "5a1fac9d4d8a89670f6fcea4",
            "id" : 10,
            "StudentNo" : 10,
            "FirstName" : "Laverne",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 26,
            "gender" : "female"
        }
        {
            "_id" : "5a1fac9dc6cf9262fcd8d346",
            "id" : 11,
            "StudentNo" : 11,
            "FirstName" : "Kerry",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 33,
            "gender" : "female"
        }
        {
            "_id" : "5a1fac9d7122a358cb8ceae2",
            "id" : 12,
            "StudentNo" : 12,
            "FirstName" : "Graham",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 24,
            "gender" : "male"
        }
        {
            "_id" : "5a1fac9d4dc7f70eb92f1da0",
            "id" : 13,
            "StudentNo" : 13,
            "FirstName" : "Carroll",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 30,
            "gender" : "male"
        }
        {
            "_id" : "5a1fac9df77cbef9874b4bf1",
            "id" : 14,
            "StudentNo" : 14,
            "FirstName" : "Esperanza",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 21,
            "gender" : "female"
        }
        {
            "_id" : "5a1fac9df2784b0f5fbf602f",
            "id" : 15,
            "StudentNo" : 15,
            "FirstName" : "Britt",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 22,
            "gender" : "male"
        }
        {
            "_id" : "5a1fac9df25fb52e6e352332",
            "id" : 16,
            "StudentNo" : 16,
            "FirstName" : "Howell",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 37,
            "gender" : "male"
        }
        {
            "_id" : "5a1fac9dc5c071813e05ca59",
            "id" : 17,
            "StudentNo" : 17,
            "FirstName" : "Josefina",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 35,
            "gender" : "female"
        }
        {
            "_id" : "5a1fac9d1770a92607129bb3",
            "id" : 18,
            "StudentNo" : 18,
            "FirstName" : "Gilbert",
            "LastName" : "<ReferenceError: flastName is not defined>",
            "age" : 31,
            "gender" : "male"
        }
        > 

# Find the number of female and male

    db.students.aggregate(
        [
            {
                $group : {_id : "$gender" ,MyResult : {$sum : 1}}
            }
        ]
    )

    { "_id" : "male", "MyResult" : 9 }
    { "_id" : "female", "MyResult" : 10 }
    > 

# Find max age 

    db.students.aggregate(      
        [
            {
                $group : {_id : "$gender" ,MaxAge : {$max : "$age"}}
            }
        ]
    )

    { "_id" : "male", "MaxAge" : 39 }
    { "_id" : "female", "MaxAge" : 38 }

    > 
# Find min age 

    db.students.aggregate(      
        [
            {
                $group : {_id : "$gender" ,MinAge : {$min : "$age"}}
            }
        ]
    )

    { "_id" : "male", "MinAge" : 22 }
    { "_id" : "female", "MinAge" : 21 }
    > 
