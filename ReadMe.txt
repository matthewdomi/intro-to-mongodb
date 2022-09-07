SYNTAX IN STUDIO 3T


//Version of database =>
db.version()


//Show Database =>
show dbs

//switch to admin =>
use admin

//switch to local =>
use local

//
//use school
db.createCollection("students")
//
db.createCollection("teachers")

 show collections
 
 
// insert document into collection
db.students.insertMany(
[{"firstName":"Moina","lastName":"Coltart","gender":"Female","age":6,"class":5},
{"firstName":"Leicester","lastName":"Bale","gender":"Male","age":13,"class":4},
{"firstName":"Salmon","lastName":"McQuirk","gender":"Male","age":11,"class":1},
{"firstName":"Chic","lastName":"McElvogue","gender":"Male","age":6,"class":1},
{"firstName":"Rafi","lastName":"Sherrard","gender":"Male","age":8,"class":1},
{"firstName":"Alaster","lastName":"Gudd","gender":"Male","age":12,"class":3},
{"firstName":"Noemi","lastName":"Byrd","gender":"Female","age":12,"class":6},
{"firstName":"Royce","lastName":"Kendell","gender":"Male","age":12,"class":6},
{"firstName":"Starla","lastName":"Rhule","gender":"Female","age":9,"class":5},
{"firstName":"Danna","lastName":"Kareman","gender":"Female","age":6,"class":3},
{"firstName":"Sallie","lastName":"Burtwistle","gender":"Female","age":9,"class":2},
{"firstName":"Walton","lastName":"Waliszewski","gender":"Male","age":6,"class":6},
{"firstName":"Paton","lastName":"Hanne","gender":"Male","age":8,"class":2},
{"firstName":"Carla","lastName":"Fausset","gender":"Female","age":13,"class":4},
{"firstName":"Susan","lastName":"Gollin","gender":"Female","age":12,"class":5},
{"firstName":"Gregoire","lastName":"Carmody","gender":"Male","age":12,"class":3},
{"firstName":"Emmalee","lastName":"Favel","gender":"Female","age":6,"class":2},
{"firstName":"Maryanna","lastName":"Valentine","gender":"Female","age":12,"class":2},
{"firstName":"Rae","lastName":"Pounder","gender":"Female","age":6,"class":1},
{"firstName":"Jessey","lastName":"Tunnow","gender":"Male","age":12,"class":6},
{"firstName":"Rory","lastName":"Rollason","gender":"Female","age":12,"class":4},
{"firstName":"Gavrielle","lastName":"Sear","gender":"Female","age":13,"class":6},
{"firstName":"El","lastName":"Wigsell","gender":"Male","age":13,"class":6},
{"firstName":"Tarrance","lastName":"Ingerson","gender":"Male","age":6,"class":3},
{"firstName":"Brena","lastName":"Babbage","gender":"Female","age":6,"class":1},
{"firstName":"Kessia","lastName":"Rafe","gender":"Female","age":8,"class":1},
{"firstName":"Lonny","lastName":"Ollie","gender":"Male","age":6,"class":2},
{"firstName":"Erv","lastName":"Honack","gender":"Male","age":12,"class":1},
{"firstName":"Mikey","lastName":"Figin","gender":"Male","age":6,"class":6},
{"firstName":"Clevie","lastName":"Skein","gender":"Male","age":9,"class":2},
{"firstName":"Kennie","lastName":"Nunnery","gender":"Male","age":10,"class":1},
{"firstName":"Luke","lastName":"Sallans","gender":"Male","age":13,"class":6},
{"firstName":"Ulrich","lastName":"Storch","gender":"Male","age":8,"class":5},
{"firstName":"Man","lastName":"Meade","gender":"Male","age":10,"class":3},
{"firstName":"Lianna","lastName":"Carlile","gender":"Female","age":7,"class":5},
{"firstName":"Anthe","lastName":"Milton-White","gender":"Female","age":8,"class":2},
{"firstName":"Pamela","lastName":"Di Baudi","gender":"Female","age":11,"class":6},
{"firstName":"El","lastName":"Crossley","gender":"Male","age":8,"class":4},
{"firstName":"Padraig","lastName":"Gheeorghie","gender":"Male","age":6,"class":5},
{"firstName":"Hollie","lastName":"Suller","gender":"Female","age":8,"class":1},
{"firstName":"Dix","lastName":"Bleckly","gender":"Female","age":11,"class":1},
{"firstName":"Fraser","lastName":"Cafe","gender":"Male","age":13,"class":5},
{"firstName":"Fionnula","lastName":"Janjic","gender":"Female","age":8,"class":1},
{"firstName":"Rochell","lastName":"Harries","gender":"Female","age":8,"class":1},
{"firstName":"Gayle","lastName":"Charley","gender":"Male","age":13,"class":6},
{"firstName":"Willow","lastName":"Holah","gender":"Female","age":6,"class":1},
{"firstName":"Patti","lastName":"Bompas","gender":"Female","age":13,"class":3},
{"firstName":"Emmie","lastName":"Aspling","gender":"Female","age":13,"class":2},
{"firstName":"Elnora","lastName":"Chezelle","gender":"Female","age":10,"class":1},
{"firstName":"Karna","lastName":"Bale","gender":"Female","age":9,"class":1}]
)


db.teachers.insertMany(
[{"firstName":"Danica","lastName":"Coultish","gender":"Female","email":"dcoultish0@hibu.com","class":1},
{"firstName":"Irving","lastName":"Schusterl","gender":"Male","email":"ischusterl1@huffingtonpost.com","class":2},
{"firstName":"Jorie","lastName":"Balshen","gender":"Female","email":"jbalshen2@illinois.edu","class":3},
{"firstName":"Willi","lastName":"Spykings","gender":"Female","email":"wspykings3@google.pl","class":4},
{"firstName":"Madlin","lastName":"MacKeeg","gender":"Female","email":"mmackeeg4@nbcnews.com","class":5},
{"firstName":"Reginald","lastName":"Bound","gender":"Male","email":"rbound5@hp.com","class":6}]
)

//find query => all students, gender of Male, class - 5
db.students.find({})

db.students.find({gender: "Male"})


db.students.find({class: 5})
// find query all female in class 5
db.students.find({class: 5, gender: "Female"})

//find query one female in class 5
db.students.findOne({_id:  ObjectId("6318909255c10ee4ee56cbaa") })

//Sorting and retrieving info
db.students.find({}).sort({class: -1})

db.students.find({gender: "Female", class: 1}).count()


//limit element
db.students.find({}).limit(5)


//Skip
db.students.find({}).skip(6)


//Equality Check

//greater than ($gt) and greater than or equal to ($gte)
db.students.find({
        age: {$gte: 10}
})


//or function ($or)
db.students.find({
    $or : [{gender: "Female"}, {class: 5}]
    })
    
  
  //  
db.students.find({
    class : {$in :[1,2]}
    }).sort({class : 1})
    
    