# Zuri Chat DM (Create Room API)

Connect With Us: `developer@zuri.chat`
Zuri Chat is an open source slack clone. However, it offers a lot more functionality via a plugin system where each room can be provided by a different plugin provider.
​
## **Authentication**
this API does not require any authentication for use, 

## **Errors**
When an error occurs, you will receive an error object. Most of these error objects contain an error code and an error description so that your applications can more efficiently identify the problem.
​
If you get a 4xx response code, then you can assume that there is a bad request from your end. In this case, 
check the [Standard Error Responses](#standard-error-responses) for more context.
​
5xx errors suggest a problem on server's end.
​
​
​
## API methods:
- GET
- POST

## End Points:
base url: https://dm.zuri.chat/docs/v1
### /createroom
- **Endpoint**: createroom
- **Method**: Post
- **Description**: creates a room using the id of two users so that messages can be sent between them. It can also work for one user as a user can send a message to his/herself. but the user id has to be in a list.
#### parameters: 
| Name | Data type |
|--------|-------------|
| org_id (required)| string |
| room_users_id (required) | list of strings |
| bookmarks| string |
| pinned| string |

#### how to create a room 
- use the endpoint **https://dm.zuri.chat/api/v1/createroom**
- create a json object that takes two parameters, **the organization id and a list of user ids**
- it will create a room and return the id
***please note the createroom is a post method***


##### Example: 
- ##### for two or more users

```sh
 https://dm.zuri.chat/api/v1/createroom { 
     "org_id": "ajaiu498283928928rieowe",
    "room_user_ids": ["lkdl049052098509292","al09952090529302"]
 }
```
- ##### for a user

```sh
 https://dm.zuri.chat/api/v1/createroom { 
     "org_id": "ajaiu498283928928rieowe",
    "room_user_ids": ["lkdl049052098509292", ]
 }
```
##### response:

```json
code:201
 { 
     "room_id": "61423bbc9fd1f4f655d445e7",
 }
```

``` sh
Code: 400
 Description: bad request
{
  "status": 400,
  "message": "email address is not valid"
}
```


