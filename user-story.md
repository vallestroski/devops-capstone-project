# User Story – Account Service

## Story
As a **customer of the Account Service**,  
I want to **create, read, update, and delete my account information**,  
so that **I can manage my personal data and keep it up to date**.

---

## Acceptance Criteria

### 1. Create Account
- When I send a POST request to `/accounts` with valid JSON data,  
  the service must create a new account.
- The response must include:
  - HTTP 201 CREATED
  - The created account in JSON format
  - A `Location` header pointing to the new resource

### 2. Read Account
- When I send a GET request to `/accounts/<id>`,  
  the service must return the account data if it exists.
- If the account does not exist, return:
  - HTTP 404 NOT FOUND

### 3. List Accounts
- When I send a GET request to `/accounts`,  
  the service must return a list of all accounts.
- The response must include:
  - HTTP 200 OK
  - A JSON array of accounts

### 4. Update Account
- When I send a PUT request to `/accounts/<id>` with valid JSON data,  
  the service must update the account.
- If the account does not exist, return:
  - HTTP 404 NOT FOUND

### 5. Delete Account
- When I send a DELETE request to `/accounts/<id>`,  
  the service must delete the account.
- The response must include:
  - HTTP 204 NO CONTENT

---

## Non‑Functional Requirements
- The service must run in a container on OpenShift.
- The CI/CD pipeline must:
  - Lint the code
  - Run unit tests
  - Build the container image
  - Deploy the application automatically
