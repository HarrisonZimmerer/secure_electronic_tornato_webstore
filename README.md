
# Secure Electronic Tornado Webstore

## Objective

The objective of this project was to design and build a secure web-based e-commerce application using a Tornado based web framework. The project simulates a basic online store with user session management, secure file uploads, and interaction with a MySQL based database. This was to emphasise integrating cybersecurity best practices in the areas of input sanitization, session cookies, file handling, and secure communications over HTTPS.

### Skills Learned

* Web application development with the Tornado Python framework
*  Session and cookie management with HTTP-only and secure flags
* Secure user input handling and output encoding (e.g., `tornado.escape`)
* Secure file upload handling and MIME type validation
* application of HTTPS with self-signed SSL certificates
* SQL operations and parameterization using MySQLdb
* use of best parctice mitigation strategies against:

  * Cross-site scripting (XSS)
  * SQL injection
  * Directory traversal attacks

### Tools Used

* **Python 3.x**
* **Tornado Web Framework**
* **MySQL / MySQLdb**
* **UUID** – for session and cookie identification
* **Magic** – for MIME type detection during uploads
* **HTML/CSS** – for frontend templates
* **OpenSSL** – for generating self-signed SSL certificates
* **Virtual Machines / Local Server** – for hosting and testing

---

## Steps

1. **Design & Setup**

   * Created MySQL database with tables for products, cart, and user data
   * Defined Tornado routes and handlers for home, details, cart, upload, and userform pages

2. **Session Management**

   * Implemented secure, unique UUID cookies per user (`httponly`, `Secure`)
   * Checked for existing cookies to track user carts and login status

3. **Product Display & Cart Functionality**

   * Retrieved product data from database for display on home and details pages
   * Allowed adding/removing items to/from cart with quantity tracking

4. **Security Enhancements**

   * Used `tornado.escape` and regex to sanitize inputs
   * Escaped all dynamic content in HTML templates to prevent XSS
   * Added MIME type verification for file uploads using `magic`
   * Restricted directory traversal with `os.path.basename` and file existence checks
   * Enabled HTTPS via Tornado's `ssl_options` with self-signed certs

5. **File Upload**

   * Added upload handler with file validation
   * Stored files in a secure static uploads directory
   * Rendered uploaded files with correct MIME type handling

6. **Final Deployment**

   * Hosted app locally over HTTPS
   * Tested functionality and edge cases using local browser and dev tools

---

## Credits

* Author: **JT Hamrick**
* Template inspiration from [Chris Diana Media - Simplestore](http://chrisdianamedia.com/simplestore/)

---

## Running the App

To run the server:

```bash
python main.py
```

Then visit in your browser:

```
https://<your_local_ip>:8893
```

> **Note**: Self-signed certs will require bypassing the browser security warning.

---

## License

This project was developed for academic purposes. Feel free to fork, modify, or extend for educational use.

---


