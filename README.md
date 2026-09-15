DIne QR Documentation.


Build an **MVP for a Dine-in QR Code Ordering & Order Management System**.

### 1. Goal

Customers scan a QR code placed on a restaurant table, view the digital menu, add items to cart, place an order, and track its status. Restaurant staff can manage menu items and incoming orders from an admin dashboard.

### 2. Tech Stack

* **Frontend:** React / Next.js + Tailwind CSS
* **Backend:** FastAPI (Python)
* **Database:** PostgreSQL
* **Authentication:** Simple JWT-based admin authentication
* **QR:** Generate unique QR codes for each table
* **Deployment-ready:** Docker + `.env` configuration

### 3. Customer Flow

1. Customer scans table QR code.
2. QR opens `/menu/{restaurant_id}/{table_id}`.
3. Display restaurant name, categories, menu items, prices, images and availability.
4. Customer adds items to cart.
5. Cart shows items, quantities, subtotal and total.
6. Customer enters optional name/phone or continues as guest.
7. Place order.
8. Generate unique order number.
9. Show order confirmation and current status.
10. Customer can view status: **Received → Preparing → Ready → Served**.

### 4. Admin Dashboard

Create a simple responsive dashboard with:

**Orders**

* View new/active/completed orders.
* Filter by status/table.
* View order details and ordered items.
* Change status: Received → Preparing → Ready → Served → Cancelled.
* New orders should appear without manually refreshing (polling is acceptable for MVP).

**Tables**

* Create/edit/delete tables.
* Generate/download QR code for each table.
* QR should contain the restaurant + table identifier.

**Menu**

* Create/edit/delete menu categories.
* Create/edit/delete menu items.
* Fields: name, description, price, image URL, category, availability.
* Toggle item availability.

### 5. Database Models

Implement at minimum:

* Restaurant
* Admin/User
* Table
* Category
* MenuItem
* Order
* OrderItem

Relationships must properly connect restaurant → tables/menu → orders.

### 6. API

Create clean REST APIs for:

* Restaurant/menu retrieval
* Categories and menu items
* Cart/order creation
* Order retrieval/status
* Admin authentication
* Menu CRUD
* Table CRUD
* QR generation
* Order management

Validate all request data and return consistent JSON responses.

### 7. UI Requirements

Customer UI should be **mobile-first**, fast and simple:

* Menu categories
* Item cards
* Add/remove quantity
* Sticky cart button
* Checkout
* Order confirmation/status

Admin UI should be desktop/tablet-friendly with a clean dashboard.

### 8. MVP Scope Restrictions

Do **NOT** implement initially:

* Online payments
* Delivery
* Inventory management
* Loyalty programs
* Reviews
* Complex analytics
* Multi-branch management
* POS integrations
* Customer accounts

Focus on making the **QR → Menu → Cart → Order → Kitchen/Admin → Status** flow fully functional.

### 9. Development Process

Build incrementally:

1. Set up project structure and environment.
2. Design database schema and migrations.
3. Implement backend APIs.
4. Implement customer menu/order flow.
5. Implement admin authentication/dashboard.
6. Implement menu and table management.
7. Implement QR generation.
8. Implement real-time/polling order updates.
9. Add validation, error handling and loading/empty states.
10. Test the complete end-to-end flow.

### 10. Deliverables

Provide:

* Complete source code
* Database migrations/schema
* `.env.example`
* Docker configuration
* README with setup instructions
* Seed/demo restaurant with sample menu, tables and admin account
* API documentation
* Basic automated tests for critical APIs

Keep the architecture clean and modular so features such as **online payments, kitchen display system, waiter ordering, analytics and multi-restaurant support** can be added later.
