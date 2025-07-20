# WhatsApp Web Clone

A responsive WhatsApp Web clone built with HTML, CSS, JavaScript, and PHP with MySQL database integration. This project mimics the look and feel of WhatsApp's web interface with authentication functionality.

## Features

- **Responsive Design**: Fully responsive interface that works on desktop and mobile devices
- **User Authentication**: Complete login and registration system with session management
- **WhatsApp-like Interface**: Dark theme UI matching WhatsApp's current design
- **Interactive Elements**:
  - Chat list with search functionality
  - Status updates viewer
  - Settings dropdown menu
  - Active chat highlighting
- **Security Features**:
  - Password hashing using PHP's `password_hash()`
  - Session management with configurable timeouts
  - SQL injection prevention with prepared statements
  - Form validation (client-side and server-side)

## Tech Stack

- **Frontend**: HTML5, CSS3, JavaScript (ES6+)
- **Backend**: PHP 7.4+
- **Database**: MySQL 5.7+
- **Session Management**: PHP Sessions
- **Authentication**: PHP password hashing

## Project Structure

```
whatsapp-clone/
├── index.html          # Authentication page (login/register)
├── homepage.html       # Main WhatsApp interface
├── login.php          # Login processing
├── register.php       # Registration processing
├── logout.php         # Logout functionality
├── paste.txt          # Main interface HTML
├── paste-2.txt        # Authentication page HTML
└── README.md          # This file
```

## Database Schema

```sql
CREATE DATABASE whatsapp;
USE whatsapp;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL
);
```

## Installation & Setup

### Prerequisites

- PHP 7.4 or higher
- MySQL 5.7 or higher
- Web server (Apache/Nginx) or XAMPP/WAMP/MAMP
- Modern web browser

### Step 1: Database Setup

1. Create a MySQL database named `whatsapp`
2. Execute the following SQL to create the users table:

```sql
CREATE DATABASE whatsapp;
USE whatsapp;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL
);
```

### Step 2: Configure Database Connection

Update the database configuration in `login.php` and `register.php`:

```php
// Database configuration
$host = 'localhost';        // Your MySQL host
$dbname = 'whatsapp';      // Database name
$username = 'root';         // Your MySQL username
$password = '';            // Your MySQL password
```

### Step 3: File Setup

1. Clone or download the project files
2. Place all files in your web server's document root (e.g., `htdocs` for XAMPP)
3. Ensure PHP has write permissions for session management

### Step 4: Run the Application

1. Start your web server and MySQL
2. Navigate to `http://localhost/your-project-folder/index.html`
3. Create a new account or login with existing credentials

## Usage

### Registration
1. Open the application in your browser
2. Click "Register" to switch to registration mode
3. Fill in your details (first name, last name, email, password)
4. Submit the form to create your account
5. You'll be automatically logged in and redirected to the main interface

### Login
1. Enter your email and password
2. Optionally check "Keep me Logged in" for extended session
3. Click "Log in" to access the main interface

### Main Interface Features
- **Chat List**: Browse through your chat conversations
- **Search**: Use the search box to filter chats
- **Status Updates**: Click the status button (📊) to view status updates
- **Settings**: Click the settings gear (⚙) for dropdown options
- **Logout**: Use the logout button to end your session

## Configuration Options

### Session Management
- **Regular Login**: 2-hour session timeout
- **Keep Logged In**: 30-day session timeout

### Security Features
- Passwords are hashed using `PASSWORD_DEFAULT` algorithm
- Email validation on both client and server side
- SQL injection prevention using PDO prepared statements
- CSRF protection through form handling

## Browser Compatibility

- Chrome 70+
- Firefox 65+
- Safari 12+
- Edge 79+

## Development Notes

### Responsive Design
The interface adapts to different screen sizes:
- Desktop: Side-by-side layout with full sidebar
- Mobile: Stacked layout with collapsible sidebar

### JavaScript Features
- Real-time search functionality
- Dynamic UI state management
- Modal window controls
- Form validation

### PHP Security
- Password hashing with `password_hash()`
- Input sanitization with `trim()` and validation
- Error handling with try-catch blocks
- Session security configuration

## Known Limitations

- This is a UI clone only - no real messaging functionality
- No database schema for messages, contacts, or groups
- No real-time messaging (WebSocket) implementation
- No file upload/media sharing capabilities
- No push notifications

## Future Enhancements

- Real-time messaging with WebSocket
- Message storage and retrieval
- Contact management system
- Group chat functionality
- File and media sharing
- Push notifications
- Mobile app version

## Troubleshooting

### Common Issues

1. **Database Connection Error**
   - Check MySQL is running
   - Verify database credentials in PHP files
   - Ensure `whatsapp` database exists

2. **Session Issues**
   - Check PHP session configuration
   - Ensure web server has write permissions
   - Clear browser cookies if needed

3. **Form Submission Problems**
   - Verify PHP files are in correct location
   - Check browser console for JavaScript errors
   - Ensure all required fields are filled

4. **Styling Issues**
   - Clear browser cache
   - Check CSS file paths
   - Verify all HTML files are properly linked

## License

This project is for educational purposes only. WhatsApp is a trademark of Meta Platforms, Inc.

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## Support

For issues or questions, please check the troubleshooting section above or review the code comments for implementation details.