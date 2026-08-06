--- README.md (原始)


+++ README.md (修改后)
# Professional ERP & Accounting System

A comprehensive, professional ERP and accounting system built with PHP Native 8.2 and MySQL.

## Features

### Core Modules
- **Dashboard** - Real-time statistics and overview
- **Product Management** - Complete inventory control
- **Warehouse Management** - Multi-warehouse support
- **Sales Management** - Invoice generation and tracking
- **Purchase Management** - Supplier invoices
- **Customer Management** - CRM features
- **Supplier Management** - Vendor tracking
- **Accounting** - Full double-entry bookkeeping
- **Reports** - Comprehensive business reports
- **User Management** - Role-based access control

### Technical Features
- PHP Native 8.2 (No Framework)
- MySQL Database
- MVC Architecture
- OOP Design Pattern
- RTL Support (Persian/Dari)
- Responsive Design (Bootstrap 5)
- Dark/Light Mode Ready
- AJAX Functionality
- Security Features (SQL Injection Prevention, XSS Protection)
- Session Management
- Password Encryption

## Installation

### Requirements
- PHP 8.2 or higher
- MySQL 5.7 or higher / MariaDB 10.3+
- Web Server (Apache/Nginx)
- cPanel Compatible

### Setup Instructions

1. **Upload Files**
   ```
   Upload all project files to your cPanel hosting
   ```

2. **Create Database**
   - Create a new database in cPanel/phpMyAdmin
   - Create a database user with full privileges
   - Note the database credentials

3. **Import Database**
   ```
   Import database.sql file via phpMyAdmin
   ```

4. **Configure Database Connection**
   Edit `app/config.php`:
   ```php
   define('DB_HOST', 'localhost');
   define('DB_NAME', 'your_database_name');
   define('DB_USER', 'your_database_user');
   define('DB_PASS', 'your_database_password');
   ```

5. **Set Permissions**
   Ensure these directories are writable:
   ```
   storage/logs/
   storage/sessions/
   public/uploads/
   ```

6. **Access the System**
   Navigate to: `http://yourdomain.com/public/index.php`

### Default Login Credentials
- **Username:** admin
- **Password:** admin123

⚠️ **Important:** Change the default password immediately after first login!

## Project Structure

```
├── app/
│   ├── config.php          # Configuration file
│   ├── routes.php          # Application routes
│   ├── Controllers/        # Controller classes
│   ├── Core/              # Core classes (Router, Model, Controller, Database)
│   ├── Helpers/           # Helper functions
│   ├── Models/            # Model classes
│   └── Views/             # View templates
│       ├── auth/          # Authentication views
│       ├── dashboard/     # Dashboard views
│       ├── errors/        # Error pages
│       └── layouts/       # Layout templates
├── public/
│   ├── index.php          # Entry point
│   ├── assets/
│   │   ├── css/          # Stylesheets
│   │   ├── js/           # JavaScript files
│   │   └── images/       # Images
│   └── uploads/          # User uploads
├── storage/
│   ├── logs/             # Application logs
│   └── sessions/         # Session files
└── database.sql          # Database schema and seed data
```

## Database Tables

### Core Tables
- users - System users
- roles - User roles and permissions
- settings - System settings
- currencies - Currency management
- activity_logs - User activity logging

### Product & Inventory
- products - Product catalog
- categories - Product categories
- brands - Product brands
- units - Measurement units
- warehouses - Warehouse locations
- warehouse_products - Warehouse stock
- inventory_logs - Stock movements

### Sales & Customers
- customers - Customer records
- sales_invoices - Sales invoices
- sales_items - Invoice line items
- sales_returns - Return orders
- sales_return_items - Return line items

### Purchases & Suppliers
- suppliers - Supplier records
- purchase_invoices - Purchase invoices
- purchase_items - Invoice line items

### Accounting
- accounts - Bank/Cash accounts
- transactions - Financial transactions
- checks - Check management
- installments - Payment installments

## Security Features

1. **Password Hashing** - BCrypt algorithm
2. **SQL Injection Prevention** - Prepared Statements (PDO)
3. **XSS Protection** - Output escaping
4. **Session Security** - Secure session handling
5. **CSRF Protection** - Token validation (to be implemented)
6. **Input Validation** - Server-side validation
7. **Access Control** - Role-based permissions

## API Endpoints (AJAX)

- `/ajax/search/products` - Search products
- `/ajax/search/customers` - Search customers
- `/ajax/search/suppliers` - Search suppliers
- `/ajax/product/{id}` - Get product details
- `/ajax/dashboard/stats` - Dashboard statistics

## Customization

### Adding New Routes
Edit `app/routes.php`:
```php
$router->get('new-page', 'NewController@index');
```

### Creating New Controller
```php
class NewController extends Controller {
    public function index() {
        $this->requireAuth();
        $this->view('new/index', ['title' => 'New Page']);
    }
}
```

### Adding New Model
```php
class NewModel extends Model {
    protected $table = 'new_table';

    // Custom methods here
}
```

## Reports Available

1. Sales Report
2. Purchase Report
3. Inventory Report
4. Profit & Loss Statement
5. Customer Report
6. Supplier Report
7. Cash Flow Report
8. Bank Report
9. Tax Report

## Supported Languages

- Persian (Farsi) - Default
- Dari
- English (Ready for implementation)

## Browser Support

- Chrome (Latest)
- Firefox (Latest)
- Safari (Latest)
- Edge (Latest)
- Opera (Latest)

## Troubleshooting

### Common Issues

**Database Connection Error**
- Verify database credentials in config.php
- Ensure database user has proper permissions
- Check if database server is running

**Permission Denied**
- Set correct permissions on storage/ and public/uploads/
- CHMOD 755 for directories, 644 for files

**Blank Page**
- Check error logs in storage/logs/
- Enable error reporting in config.php (development only)

**Session Issues**
- Ensure storage/sessions/ is writable
- Check PHP session configuration

## Support & Documentation

For additional support and documentation, please refer to the inline code comments and class documentation.

## License

This software is proprietary and confidential.

## Version

Current Version: 1.0.0

---

**Developed with ❤️ using PHP Native**
