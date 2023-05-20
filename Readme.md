# Task 1: Find all users who are located in New York.
----------
## db.users.aggregate([ { $match: {"address.city": "New York"} } ])

# Task 2: Find the user(s) with the email "johndoe@example.com" and retrieve their favorite movie.
----------
## db.users.aggregate([ { $match: {"address.city": "New York"} } ])
