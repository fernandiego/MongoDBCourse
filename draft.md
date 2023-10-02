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
