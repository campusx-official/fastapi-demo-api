# Path Parameters

**Purpose**: Used to uniquely identify a specific resource in the URL.
**Syntax:** `/patient/{id}` where `id` is dynamic and required.

### Examples:
```python
GET /patient          # All patients
GET /patient/3        # Patient with ID 3
```

### FastAPI Usage:
```python
@app.get("/patient/{patient_id}")
def get_patient(patient_id: str = Path(..., description="Patient ID", example="P01")):
    return {"patient_id": patient_id}
```

### Key Points:
- Helps fetch/update/delete specific records.
- Improves URL clarity.
- Enhanced with Path() for validation and docs.
- `...` means the parameter is compulsory.

## Path() Function

**Purpose:** Enriches path parameters with metadata, constraints, and documentation.
### FastAPI Usage:
```python
patient_id: str = Path(..., description="Patient ID", example="P001")
```
### Key Points:
- Improves documentation
- Used to fetch/update/delete specific resources.
- Validated with Path().
- `...` means the parameter is compulsory.
- Adds descriptions, examples, and validation rules (length, pattern, etc.)
 

 
# HTTP Status Codes
**Definition:** Three-digit codes returned by the server to indicate the result of a client's request.

### Categories:
**2xx (Success)**
- `200 OK:` Request processed successfully.
- `201 Created:` Resource successfully created (used in POST).
- `204 No Content:` Success, but no content returned (used in DELETE).
**3xx (Redirection)**
- Indicates further action is needed to complete the request.
**4xx (Client Errors)**
- `400 Bad Request:` The request is invalid (e.g., missing fields, wrong data types).
- `401 Unauthorized:` Authentication is required.
- `403 Forbidden:` Authenticated but not allowed to access the resource.
- `404 Not Found:` Requested resource does not exist.
**5xx (Server Errors)**
- `500 Internal Server Error:` Server encountered an unexpected condition.
- `502 Bad Gateway:` Invalid response from upstream server.
- `503 Service Unavailable:` Server is down or overloaded.

### FastAPI Usage
- Use `HTTPException` to return appropriate status codes:
```python
from fastapi import HTTPException
raise HTTPException(status_code=404, detail="Patient not found")
```


# Query Parameters
- **Purpose:** Optional parameters used for filtering, sorting, pagination, etc., added after ? in the URL.
- **Syntax:** `/view?sort_by=weight&order=desc`

### FastAPI Usage:
```python
@app.get("/view")
def sort_patients(
    sort_by: str = Query(..., description="Sort field", example="weight"),
    order: str = Query("ascending", description="Sort order")
):
    return {"sort_by": sort_by, "order": order}
```

### Key Points:
- Provide flexibility without altering endpoint paths.
- Optional and can be given default values.
- Enhanced with Query() for validation and docs.