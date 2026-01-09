# Customers API Reference

**Base URL:** `/customers`

## Endpoints

### 1. List All Customers

Retrieves a list of all customer records.

* **Method:** `GET`
* **Path:** `/customers/`
* **Response:** `200 OK` (Array of Customer objects)

### 2. Create Customer

Adds a new customer to the database.

* **Method:** `POST`
* **Path:** `/customers/`
* **Request Body:** `application/json` (See Schema below)
* **Response:** `201 Created`

### 3. Read Customer

Get details for a specific customer by their ID.

* **Method:** `GET`
* **Path:** `/customers/{customer_id}`
* **Parameters:** * `customer_id` (integer, path, required)
* **Response:** `200 OK`

### 4. Update Customer

Modify an existing customer record.

* **Method:** `PUT`
* **Path:** `/customers/{customer_id}`
* **Parameters:** * `customer_id` (integer, path, required)
* **Request Body:** `application/json` (See Schema below)
* **Response:** `200 OK`

### 5. Delete Customer

Remove a customer from the system.

* **Method:** `DELETE`
* **Path:** `/customers/{customer_id}`
* **Parameters:** * `customer_id` (integer, path, required)
* **Response:** `200 OK`

---

## Data Schemas

### Customer Object

| Field | Type | Description |
| --- | --- | --- |
| **id** | `integer` | Unique identifier for the customer |
| **name** | `string` | Full name of the customer |
| **email** | `string` | Contact email address |
| **active** | `boolean` | Status of the customer account |

**Example Request/Response Body:**

```json
{
  "id": 0,
  "name": "string",
  "email": "string",
  "active": true
}

```

### Error Responses

**422 Validation Error**
Occurs when the request body or path parameters do not match the expected types (e.g., sending text instead of an integer for `customer_id`).

