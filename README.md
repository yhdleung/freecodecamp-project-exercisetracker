# [Exercise Tracker](https://www.freecodecamp.org/learn/apis-and-microservices/apis-and-microservices-projects/exercise-tracker)


## API endpoints

### Create a New User  
> POST /api/users  

| Param    | sample value |
| ---      | ---   |
|username|yhdleung|

```json
{"username":"yhdleung","_id":"627630c21222d306bf0b36c2"}
```

### List all users
> GET /api/users
```json
{"_id":"612109adf5860e05a3652f6b","username":"fcc_test_16295551170","__v":0},{"_id":"612109aef5860e05a3652f6d","username":"fcc_test_16295551175","__v":0},{"_id":"612109aff5860e05a3652f6f","username":"fcc_test_16295551182","__v":0},{"_id":"612109b0f5860e05a3652f71","username":"fcc_test_16295551193","__v":0},
```

### Add exercises
> POST /api/users/:_id/exercises

| Param    | sample value |
| ---      | ---   |
|:_id| 627630c21222d306bf0b36c2|
|description| writing|
|duration| 60|
|date| 2022-05-07|

```json
{
    "_id":"627630c21222d306bf0b36c2",
    "username":"yhdleung",
    "date":"Sat May 07 2022",
    "duration":60,
    "description":"writing"
}
```

### GET user's exercise log 
> GET /api/users/:_id/logs?[from][&to][&limit]  

e.g.  api/users/627630c21222d306bf0b36c2/logs
```json
{
    "_id": "627630c21222d306bf0b36c2",
    "username": "yhdleung",
    "count": 2,
    "log": [
        {
            "description": "push up",
            "duration": 60,
            "date": "Sat May 07 2022"
        },
        {
            "description": "writing",
            "duration": 60,
            "date": "Sat May 07 2022"
        }
    ]
}
```

e.g.
api/users/627630c21222d306bf0b36c2/logs?from=2022-03-10&to=2022-06-29
| Param    | sample value |
| ---      | ---   |
|from| 2022-03-10|
|to| 2022-06-29|
```json
{
    "_id": "627630c21222d306bf0b36c2",
    "username": "yhdleung",
    "from": "Thu Mar 10 2022",
    "to": "Fri Jun 10 2022",
    "count": 2,
    "log": [
        {
            "description": "push up",
            "duration": 60,
            "date": "Sat May 07 2022"
        },
        {
            "description": "writing",
            "duration": 60,
            "date": "Sat May 07 2022"
        }
    ]
}
```
