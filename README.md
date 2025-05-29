# GoRest2 - Postman API Test Collection

This project contains a **Postman collection** designed to test basic CRUD (Create, Read, Update, Delete) operations on the `Users` and `Posts` endpoints of the [GoRest API](https://gorest.co.in/).

## 📁 Collection Contents

### 🧍‍♂️ Users

| Request Name          | Method | Description                              |
|-----------------------|--------|------------------------------------------|
| GET Users List        | GET    | Retrieves the list of users.              |
| POST Create User      | POST   | Creates a new user with random name and email. |
| GET User By Id        | GET    | Retrieves a user by the `UserID` variable in the collection. |
| PUT Update User       | PUT    | Updates the user's name.                   |
| DELETE User           | DELETE | Deletes the user.                          |

### 📝 Posts

| Request Name          | Method | Description                              |
|-----------------------|--------|------------------------------------------|
| GET Post List         | GET    | Retrieves all existing posts.             |
| POST Create           | POST   | Creates a new post with random title and body. |
| GET Post By Id        | GET    | Retrieves a post by the `PostID` variable in the collection. |
| PUT Update Post       | PUT    | Updates an existing post.                  |

## 🔐 Authentication

All requests use a **Bearer Token** for authentication. The token is statically included in the collection:

> ⚠️ For real projects, it is recommended to store tokens securely using environment variables or secret managers.

## ✅ Test Scripts

Each request includes basic tests to verify response status codes. Example test:

```javascript
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

// Save the UserID for further requests
var UserID = pm.response.json().id;
pm.collectionVariables.set("UserID", UserID);
