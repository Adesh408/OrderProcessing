# Order Processing System

A Spring Boot backend for an E-commerce Order Processing System. Customers can place orders, track their status, and perform basic order operations.

## Features
- **Create Order**: Place an order with multiple items.
- **Retrieve Order**: Fetch order details by order ID.
- **Update Order Status**: Change status (PENDING, PROCESSING, SHIPPED, DELIVERED). PENDING orders auto-update to PROCESSING every 5 minutes.
- **List Orders**: Get all orders, optionally filtered by status.
- **Cancel Order**: Cancel only if order is still in PENDING status.

## Tech Stack
- Java 17
- Spring Boot 3.2+
- Spring Data JPA
- H2 Database (in-memory)
- Maven

## Getting Started

### Prerequisites
- Java 17 or higher
- Maven

### Running the Application
```sh
mvn spring-boot:run
```

The application will start on `http://localhost:8080`.

### API Endpoints
- `POST /api/orders` — Create a new order. Example body:
  ```json
  {
    "customerName": "John Doe",
    "items": "item1,item2"
  }
  ```
- `GET /api/orders/{id}` — Get order by ID
- `GET /api/orders` — List all orders
- `GET /api/orders?status=PENDING` — List orders filtered by status
- `PUT /api/orders/{id}/status?status=SHIPPED` — Update order status
- `POST /api/orders/{id}/cancel` — Cancel an order

### H2 Database Console
- Access at: `http://localhost:8080/h2-console`
- JDBC URL: `jdbc:h2:mem:ordersdb`
- User: `sa` (no password)

### Running Tests
```sh
mvn test
```

## AI Assistance Disclosure
This project was developed with extensive assistance from AI tools (such as Cursor AI and ChatGPT), including code generation, design, and troubleshooting. All code was reviewed and corrected as needed.


