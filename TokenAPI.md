Token API
=====================
##Description
----------------------------------
Token API is used to request token's information in database

##Payload get Token information
----------------------------------
__Payload:__

* _id(String)_: Unique identifier of token.
* _name(String)_: Name of token.
* _email(String)_: Email of token's user.
* _password(String)_: Password of user.
* _is\_active(Integer)_: State of user (0-Disable; 1-Active; 2-Administrator Disabled).
* _scan\_role(Boolean)_: Permission scanning file (True; False).
* _sandbox\_role(Boolean)_: Permission using sandbox (True; False).
* _limit(Integer)_: Number of items on one page.
* _page(Integer)_: Number of the page.
* _order(String)_: Sort field name ('asc'; 'desc').
* _search(String)_: Search by name or token.

__URL request__:  http://vccloud-av.marathon.mesos.vn/api/v1/admin/tokens

__X-API-KEY__: 
```
{
'X-API-KEY':'7caa3f58cf699c221abfc7dd65980352'
}
```

##Get Token [GET/tokens]
----------------------------------
* __Payload__:
``` 
{
    'limit': 10,
    'page': 1,
    'order': 'asc',
    'sort': 'create_date',
    'search': ''
 }
```
* __Request__ (application/x-www-form-urlencoded)
* __Response__ 200 (application/json):
```
[
    {
            "create_person": "test@vccorp.vn", 
            "create_date": "2016-10-15 02:10:57", 
            "name": "WebToken", 
            "is_active": 1, 
            "token": "7caa3f58cf699c221abfc7dd65980352", 
            "role": {"is_sandbox": false, "is_scan": true}, 
            "id": "58019032tu4jw7h0erccae898"
     }
 ]
 ```

##Edit Token [PUT/tokens]
----------------------------------
* __Request__ (application/x-www-form-urlencoded):
```
{
    'id': '58044a948627bd000bf2ccc2',
    'name': 'Token3',
    'is_active': 0,
    'scan_role': True,
    'sandbox_role': False
}
```
* __Response__ 200 (application/json):
```
    {
        "message":"Successfully."
    }
```

##Add Token [POST/tokens]
----------------------------------
* __Request__ (application/x-www-form-urlencoded):
```
{
    'name': 'WebToken',
    'email': 'test@vccorp.vn',
    'is_active': 1,
    'scan_role': True,
    'sandbox_role': False
}
```
* __Response__ 200 (application/json):
```
{
    "message":"Successfully."
}
```

##Common Responses
---------------------------------
- 200
```
    {
        "message":"Successfully."
    }
```
- 400
```
    {
      "error": "Bad Request."
      "message": "Error Description"
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