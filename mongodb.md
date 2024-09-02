<!-- create a database -->

use contact

<!-- create a collection and  -->

db.contactlist.insertMany({
[ { firstName: "Moris", lastName: "Ben", email: "ben@gmail.com", age:26 },{ firstName: "seif", lastName: "Kefi", email: "kefi@gmail.com", age:15 },{ firstName: "brouge", lastName: "Emilie", email: "emilie.b@gmail.com", age:40 }, { firstName: "brown", lastName: "Alex", age: 4 }, { firstName: "Washington", lastName: "Denzel", age:3}]
})

<!-- Display all the information about only one person using his ID. -->

db.contactlist.find({ \_id: ObjectId('66d62154c90728c9310fa011')})

<!-- Display all the contacts with an age >18. -->

db.contactlist.find({age : { $gt: 18}})

<!-- Display all the contacts with an age>18 and name containing "ah". -->

db.contactlist.find({ $and: [{ age: { $lt: 18}}, {firstName: 'Washington'},]})

<!-- Change the contact's first name from"Kefi Seif" to "Kefi Anis". -->

db.contactlist.updateOne({lastName: "Kefi"},{$set: { firstName: "Anis"}})

<!-- Delete the contacts that are aged under <5. -->

db.contactlist.deleteMany({ age: { $lt: 5}})

<!-- Display all of the contacts list. -->

db.contactlist.find()
