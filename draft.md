db.customer.insertOne({
"name": "Juan Bruce",
"age": "44",
"city": "Las vegas, United States",
"hobbies": ["Swimming", "Reading"]})

db.customer.insertOne({
    "name": "Fox", "age": "36",
    "city": "Fortaleza, Ceará, Brazil",
    "hobbies": ["Swimming", "Reading"]})

db.customer.find()
db.customer.find({name: 'Fox'})

db.createUser({
  user: "admin",
  pwd: "admin",
  roles: [{ role: "readWrite", db: "testdb" }]
})

db.customer.updateOne({_id: '651ad686eab11f5547346158'}, {$set: {name: 'Fernando'}})
651ad686eab11f5547346158

db.customer.updateOne({name: 'Diego'},{$set: {name: 'Fernando'}})


[
  {
    name: 'Deborah Allen',
    age: 22,
    city: 'Las Vegas, United States',
    location: [ 40.8584, 1.2945 ],
    hobbies: [ 'Swimming', 'Painting' ]
  },
  {
    name: 'Angela Perez',
    age: 25,
    city: 'New York, United States',
    location: [ 31.4782, 1.2245 ],
    hobbies: [ 'Woodworking', 'Reading' ]
  },
  {
    name: 'Michael Dsouza',
    age: 23,
    city: 'San Jose, United States',
    location: [ 40.6892, 74.0445 ],
    hobbies: [ 'Dancing' ]
  },
  {
    name: 'Lauren Shaw',
    age: 20,
    city: 'New Jersey, United States',
    location: [ 21.3387, 36.7645 ],
    hobbies: [ 'Cooking' ]
  },
  {
    name: 'Lewis Fisher',
    age: 33,
    city: 'San Jose, United States',
    location: [ 40.6892, 74.0445 ],
    hobbies: [ 'Dancing' ]
  },
  {
    name: 'Nina Jekins',
    age: 29,
    city: 'San Francisco, United States',
    location: [ 39.3367, 71.0345 ],
    hobbies: [ 'Coding' ]
  },
  {
    name: 'Michael Bura',
    age: 32,
    city: 'Utah, United States',
    location: [ 48.8584, 2.2945 ],
    hobbies: [ 'Writing', 'Dancing' ]
  },
  {
    name: 'Michael Baker',
    age: 39,
    city: 'San Francisco, United States',
    location: [ 39.3367, 71.0345 ],
    hobbies: [ 'Dancing' ]
  }
]

db.customer.find({$or: [{city: 'San Jose, United States'},{age: {$gte:'23'} }]})

db.customer.updateMany(
    {city: 'San Jose, United States'}, 
    {$set: {education: {
        university: 'California university', 
                start: '02-2015', 
                degree: 'BBA'}}})

db.customer.find({ hobbies: { $in: ['Dancing', 'Swimming'] } })

db.customer.find({'location.0': {$gt: 74}})

db.customer.find({name: 'Deborah Allen'}, {name: 1}) only the field name with id

db.customer.find({name: 'Deborah Allen'}, {name: 1, _id: 0}) only field name

db.customer.find({name: 'Deborah Allen'}, {name: 0}) all the other fields

db.customer.find(
  { city: 'Las Vegas, United States' },
  { name: 1, hobbies: 1, city: 1, _id: 0 }
)
display only _id, name, hobbies and city(Las vegas specifically)

var cursor = db.customer.find()

jobapp> var array = cursor.toArray()

jobapp> array[3]

db.customer.insertMany([
  {
    _id: ObjectId("63b25784bd3738edb929bca7"),
    name: 'John Bruce',
    age: 44,
    city: 'Las Vegas, United States',
    location: [ 48.8584, 2.2945 ],
    hobbies: [ 'Swimming', 'Reading' ]
  },
  {
    _id: 1,
    name: 'John Bruce',
    age: 44,
    city: 'Las Vegas, United States',
    location: [ 48.8584, 2.2945 ],
    hobbies: [ 'Swimming', 'Reading' ]
  },
  {
    _id: ObjectId("63b25d8abd3738edb929bca8"),
    name: 'Michael Dsouza',
    age: 23,
    city: 'San Jose, United States',
    location: [ 40.6892, 74.0445 ],
    hobbies: [ 'Dancing' ]
  },
  {
    _id: ObjectId("63b25edcbd3738edb929bca9"),
    name: 'Michael Dsouza',
    age: 23,
    city: 'San Jose, United States',
    location: [ 40.6892, 74.0445 ],
    hobbies: [ 'Dancing' ]
  },
  {
    _id: 123,
    name: 'Michael Dsouza',
    age: 23,
    city: 'San Jose, United States',
    location: [ 40.6892, 74.0445 ],
    hobbies: [ 'Dancing' ]
  },
  {
    _id: ObjectId("63b2623bbd3738edb929bcaa"),
    name: 'Nina Jekins',
    age: 29,
    city: 'San Francisco, United States',
    location: [ 40.6892, 74.0445 ],
    hobbies: [ 'Coding' ]
  },
  {
    _id: ObjectId("63b2623bbd3738edb929bcab"),
    name: 'Michael bura',
    age: 32,
    city: 'Utah, United States',
    location: [ 48.8584, 2.2945 ],
    hobbies: [ 'Writing', 'Dancing' ]
  }
])

db.customer.updateMany({_id: 123}, {$inc: {age: -1, score: 1}})

// Increment 'age' by 2 for all documents
db.customer.updateMany({}, { $inc: { age: 2 } })

db.customer.updateMany({name: 'Alice Johnson'}, {$max: {age: 20}})

db.customer.updateMany({name: 'Michael Dsouza'}, {$rename: {pionts: 'points'}})

db.customer.updateMany({name: 'Michael Dsouza'}, {$unset: {points: ''}})

db.customer.updateMany({name: 'Fernando'}, {$set: {points: 10}}, {upsert: true})

[
  {
    _id: ObjectId("63b25784bd3738edb929bca7"),
    name: 'John Bruce',
    age: 44,
    city: 'Las Vegas, United States',
    location: [ 48.8584, 2.2945 ],
    hobbies: [ 'Swimming', 'Reading' ],
    points: 300
  },
  {
    _id: 1,
    name: 'John Bruce',
    age: 44,
    city: 'Las Vegas, United States',
    location: [ 48.8584, 2.2945 ],
    hobbies: [ 'Swimming', 'Reading' ],
    points: 200
  },
  {
    _id: ObjectId("63b25d8abd3738edb929bca8"),
    name: 'Michael Dsouza',
    age: 23,
    city: 'San Jose, United States',
    location: [ 40.6892, 74.0445 ],
    hobbies: [ 'Dancing' ],
    points: 150
  },
  {
    _id: ObjectId("63b25edcbd3738edb929bca9"),
    name: 'Michael Dsouza',
    age: 23,
    city: 'San Jose, United States',
    location: [ 40.6892, 74.0445 ],
    hobbies: [ 'Dancing' ],
    points: 850
  },
  {
    _id: 123,
    name: 'Michael Dsouza',
    age: 23,
    city: 'San Jose, United States',
    location: [ 40.6892, 74.0445 ],
    hobbies: [ 'Dancing' ],
    points: 93
  },
  {
    _id: ObjectId("63b2623bbd3738edb929bcaa"),
    name: 'Nina Jekins',
    age: 29,
    city: 'San Francisco, United States',
    location: [ 40.6892, 74.0445 ],
    hobbies: [ 'Coding' ],
    points: 55
  },
  {
    _id: ObjectId("63b2623bbd3738edb929bcab"),
    name: 'Michael bura',
    age: 32,
    city: 'Utah, United States',
    location: [ 48.8584, 2.2945 ],
    hobbies: [ 'Writing', 'Dancing' ],
    points: 110
  },
  {
    _id: ObjectId("63b26ad9bd3738edb929bcac"),
    name: 'Michael Pele',
    age: 23,
    city: 'San Jose, United States',
    location: [ 40.6892, 74.0445 ],
    hobbies: [ 'Dancing' ],
    points: 180
  }
]

db.customer.deleteOne({_id: ObjectId('63b25784bd3738edb929bca7')})

db.customer.deleteOne({points: {$gte: 500}})

db.customer.deleteMany({points: {$lte: 500}})

db.salary.findOne({employee_id: john_id})

var john_id = db.employee.findOne({name: 'John Morgan'})._id

