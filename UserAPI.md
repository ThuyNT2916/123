User API
=====================
##Description
----------------------------------
User API is used to request user's information in database

##Payload get User information
----------------------------------
Payload are included:

* _id(String)_: Unique identifier of user.
* _fullname(String)_: Full name of user.
* _avatar_ : Avartar of user.
* _email(String)_: Email ID of user.
* _password(String)_: Password of user.
* _role(String)_: Role of users in the system ('0'-Admin; '1'-Normal User).
* _is_active(String)_: State of user ('0'-Disable; '1'-Active; '2'-Administrator Disabled).
* _limit\_size(Interger)_: Max size of file is uploaded.
* _limit\_rate(Interger)_: Max file in one time request.
* _limit(Interger)_: Number of items on one page.
* _page(Interger)_: Number of the page.
* _order(String)_: Sort field name ('asc'; 'desc').
* _sort(String)_: Sort user by field name.
* _search(String)_: Search by email or fullname of user.

##Get User [GET/users]
----------------------------------
* __Payload__:
``` 
{
    'limit': 10,
    'page': 1,
    'order': 'asc',
    'sort': 'email',
    'search': ''
 }
```
* __Request__ (application/json)
* __Response__ 200 (application/json):
```
[
{
"create_date": "2016-10-15 04:46:56", 
"avatar": "", 
"role": 1, 
"fullname": "Test", 
"config": {"limit_rate": 100000000, "limit_size": 128000000}, 
"is_active": '1', 
"id": "57f36115c2414b0683hdt230", 
"email": "test@vccorp.vn"
}
]
```

##Edit User [PUT/users]
----------------------------------
* __Request__ (application/json):
```
{
    'id': '5801abd0e101ec000a09de83',
    'fullname': 'TestEdit,
    'avatar': '',
    'email': 'testedit@vccorp.vn',
    'password': 'Abcd@3425136',
    'role': '1',
    'is_active': '1',
    'limit_size': 128000000,
    'limit_rate': 100
}
```
* __Response__200 (application/json):
```
{
    'id': '5801abd0e101ec000a09de83',
    'fullname': 'TestEdit,
    'avatar': '',
    'email': 'testedit@vccorp.vn',
    'password': 'Abcd@3425136',
    'role': '1',
    'is_active': '1',
    'limit_size': 128000000,
    'limit_rate': 100
}
```

##Add User [POST/users]
----------------------------------
* __Request__ (application/json):
```
{
    'fullname': 'Test',
    'avatar': '',
    'email': 'test@vccorp.vn',
    'password': 'Abcd@094638',
    'role': '1',
    'is_active': '1',
    'limit_size': 128000000,
    'limit_rate': 100
}
```
* __Response__ 200 (application/json)
```
{
    'fullname': 'Test',
    'avatar': '',
    'email': 'test@vccorp.vn',
    'password': 'Abcd@094638',
    'role': '1',
    'is_active': '1',
    'limit_size': 128000000,
    'limit_rate': 100
}
```

##Common Responses
---------------------------------
- 200
```
    {
        "message":"Successful."
    }
```
- 400
```
    {
      "error": "Bad Request."
    }
```
- 403
```
    {
      "error": "Forbidden."
    }
```
- 500
```
    {
      "error": "Server error occurred. Please contact to administrator."
    }
```