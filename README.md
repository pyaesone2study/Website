# MyanVolunteer - Volunteer Management Platform

**Connecting Hands, Building Hope**

A comprehensive web application for connecting volunteers with meaningful opportunities across Myanmar. Built with React, Node.js, Express, and MySQL.

---

## 📋 Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Quick Start](#quick-start)
- [Project Structure](#project-structure)
- [File Locations](#file-locations)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)

---

## ✨ Features

### For Volunteers
- ✅ User registration with Google OAuth or phone number
- ✅ Browse volunteer opportunities with filters (onsite/remote/hybrid)
- ✅ Search opportunities by category, location, and keywords
- ✅ Apply to opportunities
- ✅ Save opportunities for later
- ✅ Track application status
- ✅ Bilingual support (English & Burmese)

### For Organizations
- ✅ Create organization profile
- ✅ Post volunteer opportunities
- ✅ Manage applications (accept/decline)
- ✅ View organization statistics
- ✅ Auto-expire opportunities after deadline
- ✅ Email notifications

### General
- ✅ Responsive design (mobile & desktop)
- ✅ Real-time notifications
- ✅ Secure authentication (JWT)
- ✅ File upload for organization logos
- ✅ Automated deadline checking

---

## 🛠 Tech Stack

### Frontend
- **React 18** - UI library
- **Vite** - Build tool
- **Tailwind CSS** - Styling
- **React Router DOM** - Routing
- **React Query** - Data fetching
- **i18next** - Internationalization
- **Axios** - HTTP client
- **Lucide React** - Icons
- **React Hot Toast** - Notifications

### Backend
- **Node.js** - Runtime
- **Express.js** - Web framework
- **Sequelize** - ORM
- **MySQL** - Database
- **JWT** - Authentication
- **Bcrypt** - Password hashing
- **Nodemailer** - Email service
- **Multer** - File uploads
- **Node-Cron** - Scheduled tasks

---

## 🚀 Quick Start

### Prerequisites
```bash
node --version  # v18+
mysql --version # v8.0+
```

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/myanvolunteer.git
cd myanvolunteer
```

### 2. Setup Database
```bash
mysql -u root -p
```
```sql
CREATE DATABASE myanvolunteer CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
EXIT;
```
```bash
mysql -u root -p myanvolunteer < database/schema.sql
```

### 3. Backend Setup
```bash
cd backend
npm install
cp .env.example .env
# Edit .env with your configuration
npm run dev
```

### 4. Frontend Setup
```bash
cd frontend
npm install
cp .env.example .env
# Edit .env with your configuration
npm run dev
```

### 5. Access Application
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000

---

## 📁 Project Structure

```
myanvolunteer/
├── frontend/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── common/
│   │   │   │   ├── Header.jsx
│   │   │   │   ├── Footer.jsx
│   │   │   │   └── Loader.jsx
│   │   │   └── volunteer/
│   │   │       └── OpportunityCard.jsx
│   │   ├── pages/
│   │   │   ├── Home.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── CreateOrganization.jsx
│   │   │   ├── OrgDashboard.jsx
│   │   │   ├── AddJob.jsx
│   │   │   └── [other pages]
│   │   ├── context/
│   │   │   ├── AuthContext.jsx
│   │   │   └── LanguageContext.jsx
│   │   ├── services/
│   │   │   ├── api.js
│   │   │   ├── authService.js
│   │   │   ├── volunteerService.js
│   │   │   └── organizationService.js
│   │   ├── config/
│   │   │   └── i18n.js
│   │   ├── styles/
│   │   │   └── index.css
│   │   ├── layouts/
│   │   │   └── MainLayout.jsx
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── package.json
│   ├── vite.config.js
│   └── tailwind.config.js
│
├── backend/
│   ├── src/
│   │   ├── config/
│   │   │   └── database.js
│   │   ├── models/
│   │   │   ├── User.js
│   │   │   ├── Volunteer.js
│   │   │   ├── Organization.js
│   │   │   ├── Opportunity.js
│   │   │   ├── Application.js
│   │   │   ├── SavedOpportunity.js
│   │   │   ├── Notification.js
│   │   │   └── index.js
│   │   ├── controllers/
│   │   │   ├── authController.js
│   │   │   ├── opportunityController.js
│   │   │   ├── organizationController.js
│   │   │   └── applicationController.js
│   │   ├── routes/
│   │   │   ├── index.js
│   │   │   ├── authRoutes.js
│   │   │   ├── opportunityRoutes.js
│   │   │   ├── organizationRoutes.js
│   │   │   ├── applicationRoutes.js
│   │   │   └── savedRoutes.js
│   │   ├── middleware/
│   │   │   ├── auth.js
│   │   │   ├── errorHandler.js
│   │   │   └── upload.js
│   │   ├── services/
│   │   │   └── emailService.js
│   │   ├── jobs/
│   │   │   └── deadlineChecker.js
│   │   └── app.js
│   ├── uploads/
│   │   └── logos/
│   ├── package.json
│   └── server.js
│
├── database/
│   └── schema.sql
│
├── SETUP_GUIDE.md
└── README.md
```

---

## 📝 File Locations Guide

### Where Each Code File Goes

#### Frontend Files

**Main Entry Points:**
- `frontend/public/index.html` - HTML template
- `frontend/src/main.jsx` - React entry point
- `frontend/src/App.jsx` - Main app component
- `frontend/src/styles/index.css` - Global styles

**Configuration:**
- `frontend/src/config/i18n.js` - Language configuration
- `frontend/vite.config.js` - Vite configuration
- `frontend/tailwind.config.js` - Tailwind configuration
- `frontend/package.json` - Dependencies

**Context Providers:**
- `frontend/src/context/AuthContext.jsx` - Authentication state
- `frontend/src/context/LanguageContext.jsx` - Language state

**API Services:**
- `frontend/src/services/api.js` - Axios instance
- `frontend/src/services/authService.js` - Auth API calls
- `frontend/src/services/volunteerService.js` - Volunteer API calls
- `frontend/src/services/organizationService.js` - Organization API calls

**Components:**
- `frontend/src/components/common/Header.jsx`
- `frontend/src/components/common/Footer.jsx`
- `frontend/src/components/common/Loader.jsx`
- `frontend/src/components/volunteer/OpportunityCard.jsx`

**Layouts:**
- `frontend/src/layouts/MainLayout.jsx`

**Pages:**
- `frontend/src/pages/Home.jsx`
- `frontend/src/pages/Register.jsx`
- `frontend/src/pages/Login.jsx`
- `frontend/src/pages/About.jsx`
- `frontend/src/pages/Categories.jsx`
- `frontend/src/pages/HowItWorks.jsx`
- `frontend/src/pages/Contact.jsx`
- `frontend/src/pages/Profile.jsx`
- `frontend/src/pages/CreateOrganization.jsx`
- `frontend/src/pages/OrgDashboard.jsx`
- `frontend/src/pages/AddJob.jsx`
- `frontend/src/pages/SavedOpportunities.jsx`
- `frontend/src/pages/Applications.jsx`
- `frontend/src/pages/NotFound.jsx`

#### Backend Files

**Main Entry Points:**
- `backend/server.js` - Server entry point
- `backend/src/app.js` - Express app configuration

**Configuration:**
- `backend/src/config/database.js` - Database connection
- `backend/package.json` - Dependencies
- `backend/.env` - Environment variables (create from .env.example)

**Database Models:**
- `backend/src/models/User.js`
- `backend/src/models/Volunteer.js`
- `backend/src/models/Organization.js`
- `backend/src/models/Opportunity.js`
- `backend/src/models/Application.js`
- `backend/src/models/SavedOpportunity.js`
- `backend/src/models/Notification.js`
- `backend/src/models/index.js` - Model associations

**Controllers:**
- `backend/src/controllers/authController.js`
- `backend/src/controllers/opportunityController.js`
- `backend/src/controllers/organizationController.js`
- `backend/src/controllers/applicationController.js`

**Routes:**
- `backend/src/routes/index.js` - Main router
- `backend/src/routes/authRoutes.js`
- `backend/src/routes/opportunityRoutes.js`
- `backend/src/routes/organizationRoutes.js`
- `backend/src/routes/applicationRoutes.js`
- `backend/src/routes/savedRoutes.js`

**Middleware:**
- `backend/src/middleware/auth.js` - JWT authentication
- `backend/src/middleware/errorHandler.js` - Error handling
- `backend/src/middleware/upload.js` - File upload (Multer)

**Services:**
- `backend/src/services/emailService.js` - Email notifications

**Background Jobs:**
- `backend/src/jobs/deadlineChecker.js` - Check expired opportunities

#### Database Files
- `database/schema.sql` - Complete MySQL schema with sample data

---

## 🔌 API Documentation

### Base URL
```
http://localhost:5000/api
```

### Authentication Endpoints

#### Register
```http
POST /auth/register
Content-Type: application/json

{
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "09123456789",
  "password": "password123",
  "education": "undergraduate",
  "skills": "Communication, Leadership",
  "teamwork": true,
  "motivation": "Want to help community"
}
```

#### Login
```http
POST /auth/login
Content-Type: application/json

{
  "email": "john@example.com",
  "password": "password123"
}
```

### More API endpoints in SETUP_GUIDE.md

---

## 🔒 Environment Variables

### Frontend (.env)
```env
VITE_API_URL=http://localhost:5000/api
VITE_GOOGLE_CLIENT_ID=your_google_client_id
```

### Backend (.env)
```env
NODE_ENV=development
PORT=5000
DB_HOST=localhost
DB_NAME=myanvolunteer
DB_USER=root
DB_PASSWORD=your_password
JWT_SECRET=your_jwt_secret_min_32_chars
SMTP_HOST=smtp.gmail.com
SMTP_USER=your_email@gmail.com
SMTP_PASSWORD=your_app_password
FRONTEND_URL=http://localhost:3000
```

---

## 📖 Usage

### For Volunteers
1. Register an account
2. Browse opportunities
3. Apply to opportunities
4. Track application status

### For Organizations
1. Register as volunteer first
2. Create organization profile
3. Post opportunities
4. Manage applications

### For Admin Creation
   node scripts\createAdmin.js
---

### For Website 
    lt --port 3000
    lt --port 5000
    
## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a pull request

---

## 📄 License

This project is for educational purposes.

---

## 👥 Support

For questions or issues:
- Email: contact@myanvolunteer.org
- Issues: GitHub Issues

---

## 🙏 Acknowledgments

- Inspired by Idealist.org
- Built for Myanmar volunteer community
- Thanks to all contributors

---

**Made with ❤️ for Myanmar**
