````markdown
# Smart Edu - Educational Learning Portal

A full-stack learning management system built with Node.js, Express, MongoDB, and EJS.

## 🎓 About

Smart Edu is an educational portal that enables instructors to create and manage courses while allowing students to discover and enroll in classes. The platform features role-based access control with support for students, teachers, and administrators.

## ✨ Features

### Authentication & Authorization

- User registration with email validation
- Secure login with bcrypt password hashing
- Session-based authentication with MongoDB store
- Role-based access control (Student, Teacher, Admin)

### Course Management

- Teachers can create and manage courses
- Categorized course organization
- URL-friendly course slugs
- Full-text course search and filtering
- Student enrollment/unenrollment

### User Dashboard

- Personalized dashboard for each user role
- View created courses (for teachers)
- View enrolled courses (for students)
- User and category management (for admins)
- Delete courses and user accounts

### Additional Features

- Contact form with email notifications
- Platform statistics on homepage
- Flash messaging system for user feedback
- Responsive Bootstrap UI

## 🛠️ Tech Stack

### Backend

- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB
- **ODM:** Mongoose
- **Template Engine:** EJS

### Security & Utilities

- **Password Hashing:** bcrypt
- **Validation:** express-validator
- **Email:** Nodemailer
- **URL Slugs:** Slugify
- **Session Store:** connect-mongo
- **Flash Messages:** connect-flash

## 📦 Installation

### Prerequisites

- Node.js (v14 or higher)
- MongoDB (local or cloud instance)
- npm or yarn

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/EsmailSarwari/smart-edu.git
   cd smart-edu
   ```
````

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Create a `.env` file** in the root directory:

   ```
   PORT=3000
   MONGODB_URI=mongodb://localhost:27017/smart-edu
   ```

4. **Start the server**

   ```bash
   npm start
   ```

5. **Access the application**
   Open your browser and navigate to `http://localhost:3000`

## 📁 Project Structure

```
smart-edu/
├── controllers/          # Business logic for routes
│   ├── authController.js
│   ├── courseController.js
│   ├── categoryController.js
│   └── pageController.js
├── models/              # Mongoose schemas
│   ├── userModel.js
│   ├── courseModel.js
│   └── categoryModel.js
├── routes/              # API endpoint definitions
│   ├── userRoutes.js
│   ├── courseRoutes.js
│   ├── categoryRoutes.js
│   └── pageRoutes.js
├── middlewares/         # Authentication & authorization
│   ├── authMiddleware.js
│   ├── roleMiddleware.js
│   └── redirectMiddleware.js
├── views/               # EJS templates
├── public/              # Static assets (CSS, JS, images)
├── app.js              # Application entry point
├── package.json        # Dependencies
└── README.md           # This file
```

## 🔐 User Roles

### Student

- Register and login
- Browse all courses
- Search courses by category or keyword
- Enroll in courses
- View enrolled courses in dashboard
- Unenroll from courses

### Teacher

- All student features
- Create new courses
- Assign courses to categories
- Manage created courses
- Delete courses

### Admin

- All teacher features
- View all users
- Delete user accounts
- Access full dashboard with statistics

## 🚀 API Endpoints

### Authentication

- `POST /users/singup` — Register a new user
- `POST /users/login` — Login user
- `GET /users/logout` — Logout user

### User Dashboard

- `GET /users/dashboard` — View personalized dashboard

### Courses

- `GET /courses` — Get all courses (with search/filter)
- `GET /courses/:slug` — Get course details
- `POST /courses` — Create new course (Teacher/Admin)
- `POST /courses/enroll` — Enroll in a course
- `POST /courses/release` — Unenroll from a course
- `DELETE /courses/:slug` — Delete a course

### Pages

- `GET /` — Homepage
- `GET /about` — About page
- `GET /register` — Registration page
- `GET /login` — Login page
- `GET /contact` — Contact page
- `POST /contact` — Send contact message

## 🔑 Key Features Explained

### Password Security

Passwords are automatically hashed using bcrypt before storage. The hashing occurs in the user model's pre-save middleware.

### Course Slugs

Course names are automatically converted to URL-friendly slugs (e.g., "Web Development" → "web-development") for clean URLs.

### Session Management

User sessions are stored in MongoDB, persisting across server restarts and allowing session sharing across multiple instances.

### Flash Messages

User feedback (success/error messages) is displayed using the flash messaging system for better UX.

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 🐛 Issues & Feedback

Found a bug or have suggestions? Please open an issue on [GitHub Issues](https://github.com/EsmailSarwari/smart-edu/issues).

## 📚 Learning Resources

- [Express.js Documentation](https://expressjs.com/)
- [MongoDB Documentation](https://docs.mongodb.com/)
- [Mongoose Documentation](https://mongoosejs.com/)
- [EJS Documentation](https://ejs.co/)
