# Python API Backend
A FastAPI-based backend API built with Python 3.13.7. This project provides a RESTful API with user and product management endpoints.

## 🚀 Features
- FastAPI Framework: High-performance web framework for building APIs

- Python 3.13: Built with the latest Python version

- RESTful Endpoints: CRUD operations for users and products

- Automatic Documentation: Interactive API docs with Swagger UI and ReDoc

- CORS Enabled: Cross-origin requests support

- In-memory Storage: Simple data persistence (can be extended to database)

## 📋 Prerequisites
- Python 3.13+

- pip (Python package manager)

- macOS (developed and tested on Mac)

## 🛠️ Installation
Clone or create the project directory:

```bash
mkdir python-api-backend
cd python-api-backend
```
Create virtual environment:

```bash
python3 -m venv venv
```
Activate virtual environment:

```bash
source venv/bin/activate
```
Install dependencies:

```bash
pip install fastapi uvicorn sqlalchemy python-jose passlib python-multipart cryptography
```

Or install from requirements.txt:

```bash
pip install -r requirements.txt
```

## 📁 Project Structure
text
python-api-backend/
├── main.py              # Main application file
├── requirements.txt     # Python dependencies
├── venv/               # Virtual environment
└── README.md           # This file
🚀 Running the Application
Make sure virtual environment is activated:

```bash
source venv/bin/activate
``` 

Start the server:

```bash
uvicorn main:app --reload --host 0.0.0.0 --port 8000
``` 

- The API will be available at:

- Main endpoint: http://localhost:8000

- Interactive docs: http://localhost:8000/docs

- Alternative docs: http://localhost:8000/redoc

- Health check: http://localhost:8000/health

## 📊 API Endpoints
### Health Check
GET /health - Check API status and Python version

### Users
POST /users/ - Create a new user (JSON body)

POST /users/query/ - Create a new user (query parameters)

GET /users/ - Get all users

GET /users/{user_id} - Get user by ID

### Products
POST /products/ - Create a new product (JSON body)

POST /products/query/ - Create a new product (query parameters)

GET /products/ - Get all products

GET /products/{product_id} - Get product by ID

## 🧪 Usage Examples
Using curl with JSON (Recommended)
- Create a user:

```bash
curl -X POST "http://localhost:8000/users/" \
     -H "Content-Type: application/json" \
     -d '{"name": "John Doe", "email": "john@example.com", "age": 30}'
```
- Create a product:

```bash
curl -X POST "http://localhost:8000/products/" \
     -H "Content-Type: application/json" \
     -d '{"name": "Laptop", "price": 999.99, "category": "Electronics"}'
```
- Get all users:

```bash
curl http://localhost:8000/users/
```

- Get specific user:

```bash
curl http://localhost:8000/users/1
```
- Using Query Parameters
- Create user with query:

```bash
curl -X POST "http://localhost:8000/users/query/?name=Jane%20Doe&email=jane@example.com&age=25"
```

- Create product with query:

```bash
curl -X POST "http://localhost:8000/products/query/?name=Phone&price=599.99&category=Electronics"
```

- Using Interactive Documentation
- Visit http://localhost:8000/docs

- Expand any endpoint section

- Click "Try it out"

- Enter required parameters

- Click "Execute"

## 🔧 Development
Virtual Environment Management
- Activate virtual environment:

```bash
source venv/bin/activate
``` 
- Deactivate virtual environment:

```bash
deactivate
```
- Install new package:

```bash
pip install <package-name>
```
- Freeze requirements:

```bash 
pip freeze > requirements.txt
``` 
- Testing
The API includes automatic interactive documentation. You can test all endpoints directly from:

Swagger UI: http://localhost:8000/docs

ReDoc: http://localhost:8000/redoc

## 🗃️ Data Models
- User
```json
{
  "id": 1,
  "name": "John Doe",
  "email": "john@example.com",
  "age": 30
}
```
- Product
```json
{
  "id": 1,
  "name": "Laptop",
  "price": 999.99,
  "category": "Electronics"
}
```

## 🚨 Error Handling
- The API returns appropriate HTTP status codes:

- 200 OK - Successful request

- 201 Created - Resource created successfully

- 404 Not Found - Resource not found

- 422 Unprocessable Entity - Validation error

## 📦 Dependencies
- fastapi - Web framework for building APIs

- uvicorn - ASGI server for running FastAPI

- sqlalchemy - SQL toolkit and ORM (for future database integration)

- python-jose - JOSE implementation for Python

- passlib - Password hashing library

- python-multipart - Multipart form parsing

- cryptography - Cryptographic recipes and primitives

## 🔄 Next Steps
To extend this API, consider:

- Add database persistence (SQLite, PostgreSQL, MySQL)

- Implement authentication (JWT tokens, OAuth2)

- Add input validation and error handling

- Implement unit tests

- Add rate limiting

- Containerize with Docker

- Add logging and monitoring

## 📝 License
This project is open source and available under the MIT License.

