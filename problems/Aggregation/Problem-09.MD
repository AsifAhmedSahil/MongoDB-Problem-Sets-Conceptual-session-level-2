# MongoDB Aggregate - Problem 9

## Requirement

Find the most common favorite food among all users.

## code
db.users.aggregate([
    //Group users by their favorite movie and retrieve the average age in each movie group.
    {
        $group: {
            _id: "$favorites.food" ,
            count: {$sum : 1}
            
        }
    },
    {
        $sort: {count:-1}
    },
    {
        $limit: 1
    }
    
    ])


## Result

```result
{
  _id: 'pizza',
  totalUser: 3
}
```
