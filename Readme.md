### Task 1: Find all users who are located in New York.
---------
db.users.aggregate([
{ $match: {"address.city": "New York"} } 
])

### Task 2: Find the user(s) with the email "johndoe@example.com" and retrieve their favorite movie.
---------
db.users.aggregate([
    {$match: {email: "johndoe@example.com"}},
    {$project: {email: 1, favouriteMovie: "$favorites.movie"}}
])

### Task 3: Find all users with "pizza" as their favorite food and sort them according to age.
---------
db.users.aggregate([
    { $match: { "favorites.food": "pizza" } },
    { $sort: { age: 1 } }
])

### Task 4: Find all users over 30 whose favorite color is "green".
---------
db.users.aggregate([
   {$match: {age: {$gt: 30}, "favorites.color": "green"}},
   //project stage for clear view
   {$project: {age: 1, favouritColor: "$favorites.color"}}
])