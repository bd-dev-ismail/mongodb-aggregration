### Task 1: Find all users who are located in New York.
---------
db.users.aggregate([
{ $match: {"address.city": "New York"} } 
])