# Basic Authentication with Bcrypt

## Project Overview
This project demonstrates a secure approach to user authentication using **Node.js**, **Express**, **PostgreSQL**, and **bcrypt** for password hashing. The app allows users to register and log in with an email and password, while securely handling and storing user data. This project is intended to illustrate a basic yet secure method of managing user authentication.

---

## Features
- **User Registration**: 
  - Allows new users to create an account by entering an email and password.
  - Checks if the email is already registered to prevent duplicate accounts.
  - Uses bcrypt to hash the password before saving it to the database.

- **User Login**: 
  - Verifies the user's email and password.
  - Uses bcrypt to securely compare the entered password with the stored hash.
  - If authentication is successful, the user is granted access to a restricted area.

---

## Technologies Used
- **Node.js**: Server-side JavaScript runtime
- **Express**: Web framework for handling routing and middleware
- **PostgreSQL**: Relational database for storing user data
- **bcrypt**: Library for hashing and comparing passwords
- **dotenv**: For managing environment variables securely

---

## Project Structure
- **Views Folder**:
  - `home.ejs`: Home page with navigation options.
  - `login.ejs`: Login form for existing users.
  - `register.ejs`: Registration form for new users.
  - `secrets.ejs`: Restricted page, accessible only upon successful login.
  
- **Main Server File (`index.js`)**:
  - Contains routes for user registration, login, and access to the restricted page.
  - Includes bcrypt hashing and comparison methods to securely manage passwords.

---

## Setup Instructions
1. **Clone the Repository**: 
   - Navigate to your project directory and initialize with `git clone <repository_url>`.
   
2. **Install Dependencies**:
   - Run `npm install` to install the required packages: Express, body-parser, pg, bcrypt, dotenv.

3. **Environment Variables**:
   - Create a `.env` file in the root directory and include your database credentials:
     ```
     DB_USER=yourUsername
     DB_HOST=localhost
     DB_NAME=databaseName
     DB_PASSWORD=yourPassword
     DB_PORT=5432
     ```

4. **Set Up Database**:
   - Create a PostgreSQL database and table:
     ```sql
     CREATE TABLE authen (
         id SERIAL PRIMARY KEY,
         email VARCHAR(50) UNIQUE NOT NULL,
         password VARCHAR(255) NOT NULL
     );
     ```

5. **Run the Server**:
   - Start the server with `node index.js` or `nodemon index.js`.
   - Access the app at `http://localhost:3000`.

---

## Security Practices
- **Password Hashing**: 
  - Uses bcrypt to hash passwords with a salt for added security.
  - Prevents storing passwords as plain text.
  
- **Error Handling**:
  - Catches and logs errors for troubleshooting during registration and login.

---

## Future Improvements
- Implementing **session management** to maintain user authentication state.
- Adding **encryption** for enhanced security on sensitive data.
- Using **rate limiting** to prevent brute-force login attempts.

---

## Important Notes
This project is an introductory example of secure authentication using bcrypt. While it demonstrates strong password storage practices, further improvements (like encryption and session handling) are recommended for production environments.

---

## License
This project is open-source and available under the MIT License.
