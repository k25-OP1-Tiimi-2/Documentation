## REST documentation

### Purpose of this document
The document describes REST services provided by Tiimityo Spring Boot backend application.

### REST resources (services)
1. Get all products -> http://localhost:8080/rest/products  
2. Insert new product -> http://localhost:8080/rest/products 
3. Edit product -> http://localhost:8080/rest/products/{id}  
4. Delete product -> http://localhost:8080/rest/products/{id}

### REST requests and responses
1. **Get all products**  
HTTP method: GET  
API call: http://localhost:8080/rest/products  
Request body: -  
Response code: 200  
Response example:

```json
[
    {   "id":1,
        "title":"Talvitakki",
        "price":53.9,
        "color":"Violetti",
        "size":"M",
        "manufacturer":{"id":1,"name":"Rukka"},
        "productType":{"id":1,"name":"Vaate"}
    },
    {   "id":2,
        "title":"Sadetakki",
        "price":44.9,
        "color":"Keltainen",
        "size":"L",
        "manufacturer":{"id":2,"name":"Pomppa"},
        "productType":{"id":1,"name":"Vaate"}
    }       
]
```
2. **Insert new product**  
HTTP method: POST  
API call: http://localhost:8080/rest/products  
Request body:  
```json
{
    "title": "Lippalakki",
    "price": 12.9,
    "color": "Musta",
    "size": "M",
    "manufacturer": {
        "id": 1,
        "name": "Rukka"
    },
    "productType": {
        "id": 1,
        "name": "Vaate"
    }
}
```
Response code: 200  
Response example:
```json
{
    "id": 4,
    "title": "Lippalakki",
    "price": 12.9,
    "color": "Musta",
    "size": "M",
    "manufacturer": {
        "id": 1,
        "name": "Rukka"
    },
    "productType": {
        "id": 1,
        "name": "Vaate"
    }
}
```
3. **Edit product** 
HTTP method: PUT  
API call: http://localhost:8080/rest/products/{id}  
Request body:
```json
{
    "title":"Neule",
    "price":21.99,
    "color":"Turkoosi",
    "size":"S",
    "manufacturer":{"id":3,"name":"Feel Active"},
    "productType":{"id":1,"name":"Vaate"}
}
```
Response code: 200  
Response example:
```json
{
    "id": 3,
    "title":"Neule",
    "price":21.99,
    "color":"Turkoosi",
    "size":"S",
    "manufacturer":{"id":3,"name":"Feel Active"},
    "productType":{"id":1,"name":"Vaate"}
}
```
3. **Edit product** 
HTTP method: DELETE 
API call: http://localhost:8080/rest/products/{id}  
Request body: -  
Response code: 200  
Response example:
```
Product ID 4 has been deleted successfully
```
### HTTP methods