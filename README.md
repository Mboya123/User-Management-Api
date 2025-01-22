# User Management API

## Setup
1. Clone the repository
2. Run `npm install`
3. Start the server: `node index.js`
4. API will be available at `http://localhost:3000`

## API Endpoints

### Get User by ID
- **URL**: `/api/users/:id`
- **Method**: `GET`
- **URL Params**: `id=[integer]`
- **Success Response**: 
  - Code: 200
  - Content: `{ id: 1, name: "John", email: "john@example.com" }`
- **Error Response**:
  - Code: 404
  - Content: `{ message: "User not found" }`
 
    
## Setup Details

1. Clone the repository:
   ```bash
   git clone <repository-link>
   cd user-api
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the server:
   ```bash
   node index.js
   ```
4. The API will be available at `http://localhost:3000`.

## API Endpoints

### Get All Users

- **URL**: `/api/users`
- **Method**: `GET`
- **Success Response**:
  - Code: `200`
  - Content: `[{ id: 1, name: "John", email: "john@example.com" }, { id: 2, name: "Jane", email: "jane@example.com" }]`

### Get User by ID

- **URL**: `/api/users/:id`
- **Method**: `GET`
- **URL Params**: `id=[integer]`
- **Success Response**:
  - Code: `200`
  - Content: `{ id: 1, name: "John", email: "john@example.com" }`
- **Error Response**:
  - Code: `404`
  - Content: `{ message: "User not found" }`

### Create a New User

- **URL**: `/api/users`
- **Method**: `POST`
- **Request Body**:
  ```json
  {
    "name": "New User",
    "email": "newuser@example.com"
  }
  ```
- **Success Response**:
  - Code: `201`
  - Content: `{ id: 3, name: "New User", email: "newuser@example.com" }`
- **Error Response**:
  - Code: `400`
  - Content: `{ message: "Name and email are required" }`

### Update a User

- **URL**: `/api/users/:id`
- **Method**: `PUT`
- **URL Params**: `id=[integer]`
- **Request Body**:
  ```json
  {
    "name": "Updated Name",
    "email": "updated@example.com"
  }
  ```
- **Success Response**:
  - Code: `200`
  - Content: `{ id: 1, name: "Updated Name", email: "updated@example.com" }`
- **Error Response**:
  - Code: `400`
  - Content: `{ message: "Name and email are required" }`
  - Code: `404`
  - Content: `{ message: "User not found" }`

### Delete a User

- **URL**: `/api/users/:id`
- **Method**: `DELETE`
- **URL Params**: `id=[integer]`
- **Success Response**:
  - Code: `204`
- **Error Response**:
  - Code: `404`
  - Content: `{ message: "User not found" }`

## Testing the API in Postman

1. **Install Postman**: If not already installed, download and install Postman from [Postman Official Website](https://www.postman.com/).

2. **Start the API Server**: Ensure the server is running by executing:

   ```bash
   node index.js
   ```

   The server should be available at `http://localhost:3000`.

3. **Configure Requests in Postman**:

   - **Base URL**: `http://localhost:3000`

   - **Endpoints**:

     - **Get All Users**:
       - Method: `GET`
       - URL: `http://localhost:3000/api/users`
     - **Get User by ID**:
       - Method: `GET`
       - URL: `http://localhost:3000/api/users/:id`
       - Replace `:id` with the user ID.
     - **Create a New User**:
       - Method: `POST`
       - URL: `http://localhost:3000/api/users`
       - Body: Set to `raw` JSON and include:
         ```json
         {
           "name": "New User",
           "email": "newuser@example.com"
         }
         ```
     - **Update a User**:
       - Method: `PUT`
       - URL: `http://localhost:3000/api/users/:id`
       - Replace `:id` with the user ID.
       - Body: Set to `raw` JSON and include:
         ```json
         {
           "name": "Updated Name",
           "email": "updated@example.com"
         }
         ```
     - **Delete a User**:
       - Method: `DELETE`
       - URL: `http://localhost:3000/api/users/:id`
       - Replace `:id` with the user ID.

4. **Send Requests and Verify Responses**:

   - Click **Send** for each request and verify the responses.

5. **Error Handling**:

   - Verify that appropriate error messages and status codes are returned for invalid inputs or nonexistent users.

## Error Handling

All error responses are returned in the following format:

```json
{
  "message": "Error description"
}
```

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

