# piworks
## User Management Screen Specification Doc. (Technical Questionnaire)
### Description
* One page web app to list users with status and add new users to the user management system with mandatory fields.
---
## Requirements

* Spring Boot
* Spring Web
* Jpa
* Postgres/H2/MSSQL/MySql etc.
* Any frontend technology (ex. Angular)
## Behaviour of the system
* After entering the system, all users must be listed.(Wrt. to the checkbox status of Hide Disabled Users).
* There will be 2 main operations other than listing users:
1. List Users with status (all users by default). if the "Hide Disabled Users" checkbox is selected, lists only the enabled users.


<button>+ New User</button> <br><br> [+] Hide Disabled User

| ID  | User Name | Email | Enabled |
| --- | --- | --- | --- |
| 1   | AdminUser | admin@piworks.net | true |
| 2   | Test User | testuser@piworks.net | true |

2. Adding New User (on-click event)
Fields below must be filled.
<form action=""><label for="username">User name:</label> <input id="usename" name="username" type="text" /><br /><br /><label for="dname">Display name:</label> <input id="dname" name="dname" type="text" /><br /><br /><label for="phone">Phone:</label><br /><input id="phone" type="text" /><br /><br /><label for="email">Email:</label><br /><input id="email" type="text" /><br /><br /><label for="email">User Roles:</label>
  <select id="role" name="role">
<option value="g">Guest</option>
<option value="a">Admin</option>
<option value="sal">SuperAdmin</option>
</select><br /><br /><label for="email">Enabled:</label>
  <input type="checkbox" id="enable" name="enable">

3. Save User after the required fields are entered. (on-click event)

## Model
### User
* Features of the user are as follows.
1. ID (Primary Key)
2. UserName
3. DisplayName
4. PhoneNumber
5. EmailAddress
6. UserRole(Guest/Admin/SuperAdmin)
7. UserStatus(UserStatus {ENABLED,DISABLED})
## Functions
* UserController
1. User list
* method = list
* HTTP Request Type = GET
* End Point = /user
* Condition = default
2. User Save
* method =create
* HTTP Request Type = POST
* End Point = /user
* Condition = All the features of the user must come from the request, if any field is not filled, an error should be thrown.And also error should be thrown if the new user exists in the system.
