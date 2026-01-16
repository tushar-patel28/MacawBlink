# MacawBlink 🛒

A full-featured Java-based e-commerce web application built with JSP, Servlets, and Maven. MacawBlink provides a complete online shopping experience with user authentication, product browsing, shopping cart management, and order processing capabilities.

## 🎯 Overview

MacawBlink is a dynamic e-commerce platform that simulates a complete online shopping experience. Built using Java EE technologies, it demonstrates enterprise-level web application development with a focus on MVC architecture, session management, and database integration.

### Key Highlights

- **Session-Based Shopping Cart** - Maintains user cart across multiple sessions
- **User Authentication** - Secure registration and login system
- **Product Management** - Browse, search, and filter products
- **Order Processing** - Complete checkout and payment workflow
- **Admin Dashboard** - Manage products, inventory, and orders
- **Responsive Design** - Mobile-friendly user interface

## ✨ Features

### Customer Features

#### 🔐 User Management
- User registration with validation
- Secure login/logout functionality
- Session-based authentication
- Profile management
- Password encryption

#### 🛍️ Product Browsing
- View all available products
- Product detail pages
- Category-based filtering
- Search functionality
- Product image gallery
- Price and availability display

#### 🛒 Shopping Cart
- Add products to cart
- Update product quantities
- Remove items from cart
- View cart summary
- Real-time price calculation
- Session persistence

#### 💳 Checkout & Orders
- Secure checkout process
- Payment information capture
- Order confirmation
- Order history tracking
- Order status updates
- Invoice generation

### Admin Features

#### 📦 Product Management
- Add new products
- Update product details
- Delete products
- Manage product images
- Update inventory levels
- Set pricing and discounts

#### 📊 Order Management
- View all customer orders
- Update order status
- Manage shipping information
- Generate reports
- Track revenue

#### 👥 User Management
- View registered users
- Manage user accounts
- Track user activity
- Handle customer queries

## 🛠 Tech Stack

### Backend
- **Java** (JDK 8+) - Core programming language
- **Servlets** - Request handling and business logic
- **JSP** (JavaServer Pages) - Dynamic web pages
- **Maven** - Build automation and dependency management
- **JDBC** - Database connectivity
- **MySQL** - Relational database

### Frontend
- **HTML5** - Page structure
- **CSS3** - Styling and animations
- **JavaScript** - Client-side interactivity
- **Bootstrap** (Optional) - Responsive framework

### Server
- **Apache Tomcat 9+** - Web server and servlet container

## 🏗 Architecture

### MVC Pattern

```
┌─────────────────────────────────────────┐
│              Browser                    │
│         (User Interface)                │
└──────────────┬──────────────────────────┘
               │ HTTP Request/Response
               │
┌──────────────▼──────────────────────────┐
│           Controller                    │
│          (Servlets)                     │
│  - UserServlet                          │
│  - ProductServlet                       │
│  - CartServlet                          │
│  - OrderServlet                         │
└──────────────┬──────────────────────────┘
               │
      ┌────────┴────────┐
      │                 │
┌─────▼──────┐  ┌──────▼──────┐
│   Model    │  │    View     │
│  (Beans)   │  │    (JSP)    │
│            │  │             │
│ - User     │  │ - login.jsp │
│ - Product  │  │ - home.jsp  │
│ - Cart     │  │ - cart.jsp  │
│ - Order    │  │ - admin.jsp │
└─────┬──────┘  └─────────────┘
      │
┌─────▼──────────────────────────────────┐
│         Database (MySQL)               │
│  - users                               │
│  - products                            │
│  - cart                                │
│  - orders                              │
└────────────────────────────────────────┘
```

### Session Management

MacawBlink uses HttpSession to maintain user state across multiple HTTP requests:
- User authentication status
- Shopping cart items
- User preferences
- Order information

## 📁 Project Structure

```
MacawBlink/
├── src/
│   └── main/
│       ├── java/
│       │   └── com/
│       │       └── macawblink/
│       │           ├── controller/          # Servlets
│       │           │   ├── UserServlet.java
│       │           │   ├── ProductServlet.java
│       │           │   ├── CartServlet.java
│       │           │   ├── OrderServlet.java
│       │           │   └── AdminServlet.java
│       │           ├── model/               # Java Beans
│       │           │   ├── User.java
│       │           │   ├── Product.java
│       │           │   ├── Cart.java
│       │           │   └── Order.java
│       │           ├── dao/                 # Data Access Objects
│       │           │   ├── UserDAO.java
│       │           │   ├── ProductDAO.java
│       │           │   ├── CartDAO.java
│       │           │   └── OrderDAO.java
│       │           └── util/                # Utility Classes
│       │               ├── DBConnection.java
│       │               ├── PasswordUtil.java
│       │               └── Validator.java
│       ├── webapp/
│       │   ├── WEB-INF/
│       │   │   ├── web.xml                  # Deployment descriptor
│       │   │   └── lib/                     # External libraries
│       │   ├── css/                         # Stylesheets
│       │   ├── js/                          # JavaScript files
│       │   ├── images/                      # Product images
│       │   ├── index.jsp                    # Landing page
│       │   ├── login.jsp                    # Login page
│       │   ├── register.jsp                 # Registration page
│       │   ├── home.jsp                     # Main page
│       │   ├── products.jsp                 # Product listing
│       │   ├── product-detail.jsp           # Product details
│       │   ├── cart.jsp                     # Shopping cart
│       │   ├── checkout.jsp                 # Checkout page
│       │   ├── orders.jsp                   # Order history
│       │   └── admin/                       # Admin pages
│       │       ├── dashboard.jsp
│       │       ├── manage-products.jsp
│       │       └── manage-orders.jsp
│       └── resources/
│           └── application.properties       # Configuration
├── pom.xml                                  # Maven configuration
├── .gitignore
└── README.md
```

## 💻 Usage

### Customer Workflow

1. **Registration/Login**
   - Navigate to `/register.jsp` to create an account
   - Login via `/login.jsp`

2. **Browse Products**
   - View products on `/products.jsp`
   - Filter by category
   - Search by product name

3. **Add to Cart**
   - Click "Add to Cart" on product pages
   - View cart at `/cart.jsp`
   - Update quantities or remove items

4. **Checkout**
   - Proceed to `/checkout.jsp`
   - Enter shipping and payment details
   - Confirm order

5. **Track Orders**
   - View order history at `/orders.jsp`
   - Check order status and tracking

### Admin Workflow

1. **Login**
   - Access `/admin/login.jsp`
   - Use admin credentials

2. **Manage Products**
   - Add new products
   - Update existing products
   - Remove discontinued items
   - Update inventory

3. **Manage Orders**
   - View all orders
   - Update order status
   - Process refunds

## 🔌 API Endpoints

### User Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/register` | Register new user |
| POST | `/login` | User login |
| GET | `/logout` | User logout |
| GET | `/profile` | View user profile |
| POST | `/profile/update` | Update profile |

### Product Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/products` | List all products |
| GET | `/products/:id` | Get product details |
| GET | `/products/search` | Search products |
| GET | `/products/category/:cat` | Filter by category |

### Cart Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/cart` | View cart |
| POST | `/cart/add` | Add item to cart |
| POST | `/cart/update` | Update cart quantity |
| POST | `/cart/remove` | Remove item from cart |
| DELETE | `/cart/clear` | Clear entire cart |

### Order Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/checkout` | Process checkout |
| GET | `/orders` | View order history |
| GET | `/orders/:id` | Get order details |

### Admin Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/admin/login` | Admin login |
| POST | `/admin/products/add` | Add product |
| PUT | `/admin/products/:id` | Update product |
| DELETE | `/admin/products/:id` | Delete product |
| GET | `/admin/orders` | View all orders |
| PUT | `/admin/orders/:id/status` | Update order status |

## 🗄️ Database Schema

### Entity-Relationship Diagram

```
┌─────────────┐       ┌──────────────┐       ┌─────────────┐
│    Users    │       │   Products   │       │    Cart     │
├─────────────┤       ├──────────────┤       ├─────────────┤
│ user_id PK  │       │ product_id PK│       │ cart_id PK  │
│ username    │       │ product_name │       │ user_id FK  │
│ password    │       │ description  │       │ product_id FK│
│ email       │       │ price        │       │ quantity    │
│ first_name  │       │ stock_qty    │       │ added_at    │
│ last_name   │       │ category     │       └─────────────┘
│ phone       │       │ image_url    │              │
│ address     │       │ created_at   │              │
│ created_at  │       └──────────────┘              │
└─────────────┘              │                      │
       │                     │                      │
       │                     │                      │
       └─────────┬───────────┴──────────────────────┘
                 │
         ┌───────▼────────┐         ┌──────────────────┐
         │    Orders      │         │   Order Items    │
         ├────────────────┤         ├──────────────────┤
         │ order_id PK    │◄────────│ order_item_id PK │
         │ user_id FK     │         │ order_id FK      │
         │ total_amount   │         │ product_id FK    │
         │ order_status   │         │ quantity         │
         │ payment_method │         │ price            │
         │ shipping_addr  │         └──────────────────┘
         │ order_date     │
         └────────────────┘
```

## 📸 Screenshots

### Home Page
![Home Page](screenshots/home.png)

### Product Listing
![Products](screenshots/products.png)

### Shopping Cart
![Cart](screenshots/cart.png)

### Admin Dashboard
![Admin](screenshots/admin.png)

*Note: Add actual screenshots to the `/screenshots` directory*

## 🔮 Future Enhancements

### Planned Features

- [ ] **Payment Gateway Integration** (Stripe, PayPal)
- [ ] **Email Notifications** for orders and registration
- [ ] **Product Reviews and Ratings**
- [ ] **Wishlist Functionality**
- [ ] **Advanced Search** with filters
- [ ] **Order Tracking** with real-time updates
- [ ] **Multi-language Support**
- [ ] **Social Media Integration**
- [ ] **Recommendation Engine** using machine learning
- [ ] **Mobile Application** (Android/iOS)
- [ ] **RESTful API** for third-party integration
- [ ] **Advanced Analytics Dashboard**

### Technical Improvements

- [ ] Implement **Spring Framework** for dependency injection
- [ ] Add **Hibernate ORM** for database operations
- [ ] Implement **Redis** for session management
- [ ] Add **JUnit** tests for comprehensive testing
- [ ] Implement **JWT** authentication
- [ ] Add **Swagger** for API documentation
- [ ] Containerize with **Docker**
- [ ] Set up **CI/CD pipeline**

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch
   ```bash
   git checkout -b feature/YourFeature
   ```
3. Commit your changes
   ```bash
   git commit -m 'Add some feature'
   ```
4. Push to the branch
   ```bash
   git push origin feature/YourFeature
   ```
5. Open a Pull Request

### Coding Standards

- Follow Java naming conventions
- Comment your code appropriately
- Write meaningful commit messages
- Update documentation for new features
- Test thoroughly before submitting

## 🐛 Known Issues

- Session timeout needs configuration
- File upload size limit needs adjustment
- Cross-browser compatibility for older browsers

**Developer:** Tushar Patel

For issues and feature requests, please create an issue on GitHub.

## 🙏 Acknowledgments

- Apache Tomcat for the servlet container
- MySQL for database management
- Bootstrap for UI components
- Font Awesome for icons
- Stack Overflow community for support

---

**Made with ☕ and Java by Tushar Patel**

⭐ Star this repository if you find it helpful!
