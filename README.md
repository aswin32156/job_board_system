# 💼 Job Portal System

A full-stack job portal application that connects employers with job seekers. Built with React, Node.js, Express, and MongoDB.

![Job Portal](https://img.shields.io/badge/Status-Active-success)
![License](https://img.shields.io/badge/License-MIT-blue)
![Node](https://img.shields.io/badge/Node.js-18+-green)
![React](https://img.shields.io/badge/React-18.2-blue)
![MongoDB](https://img.shields.io/badge/MongoDB-6.0+-green)

## 📋 Table of Contents

- [Features](#-features)
- [Modules](#-modules)
- [Tech Stack](#-tech-stack)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Running the Application](#-running-the-application)
- [Project Structure](#-project-structure)
- [API Endpoints](#-api-endpoints)
- [Contributing](#-contributing)
- [License](#-license)

## ✨ Features

### For Candidates
- 🔍 Search and filter jobs by category, location, salary, and job type
- 📝 Create and manage professional profile
- 📄 Upload and manage resume
- 💾 Save jobs for later
- 📨 Apply to jobs with cover letter
- 📊 Track application status (Pending, Reviewed, Shortlisted, Rejected)
- 🔔 Real-time notifications for application updates
- 💡 Personalized job recommendations based on skills

### For Employers
- 📢 Post and manage job listings
- 👥 View and manage applicants
- 📋 Review candidate profiles and resumes
- ✅ Update application status
- 🏢 Create company profile with logo
- 📈 Dashboard with analytics
- 🔔 Notifications for new applications

### General
- 🔐 Secure authentication with JWT
- 📱 Fully responsive design
- 🎨 Modern UI with Tailwind CSS
- 🔒 Role-based access control
- 📧 Email verification system

## 📦 Modules

### 1. Employer Module
The Employer Module provides comprehensive tools for businesses to manage their recruitment process:
- **Company Profile Management**: Create and customize company profiles with logo, description, industry, and website
- **Job Posting**: Create detailed job listings with title, description, requirements, salary range, and job type
- **Job Management**: Edit, update status, or delete job postings
- **Dashboard Analytics**: View statistics on posted jobs, total applications, and hiring metrics
- **Applicant Overview**: Quick access to view all applicants across all job postings

### 2. Candidate Module
The Candidate Module empowers job seekers with tools to find and apply for their ideal positions:
- **Profile Management**: Build a professional profile with personal information, skills, education, and experience
- **Job Search**: Advanced search with filters for location, salary, job type, and category
- **Job Recommendations**: AI-powered job suggestions based on skills and preferences
- **Saved Jobs**: Bookmark interesting jobs to apply later
- **Application Tracking**: Monitor the status of all submitted applications in one place
- **Dashboard**: Personalized dashboard showing application statistics and recommended jobs

### 3. Resume Upload Module
The Resume Upload Module handles all document management for candidates:
- **Resume Upload**: Support for PDF, DOC, and DOCX formats
- **File Size Validation**: Maximum 5MB file size limit
- **Secure Storage**: Resumes stored securely on the server
- **Profile Picture Upload**: Upload and manage profile photos
- **Multiple Resume Versions**: Update resume anytime with new versions
- **Resume Preview**: View uploaded resume directly in the application

### 4. Application Review Module
The Application Review Module streamlines the hiring workflow for employers:
- **Applicant List View**: See all applicants for a specific job with their details
- **Resume Access**: Download and view candidate resumes directly
- **Cover Letter Review**: Read candidate cover letters submitted with applications
- **Status Management**: Update application status (Pending → Reviewed → Shortlisted → Rejected/Hired)
- **Candidate Profiles**: Access complete candidate profiles including skills, experience, and education
- **Notification System**: Automatic notifications sent to candidates when application status changes
- **Filtering & Sorting**: Filter applicants by status, sort by application date

## 🛠 Tech Stack

### Frontend
| Technology | Description |
|------------|-------------|
| React 18.2 | UI Library |
| Vite 5.0 | Build Tool |
| React Router DOM 6 | Routing |
| Tailwind CSS 3.4 | Styling |
| Axios | HTTP Client |
| Lucide React | Icons |
| React Hot Toast | Notifications |

### Backend
| Technology | Description |
|------------|-------------|
| Node.js | Runtime |
| Express.js | Web Framework |
| MongoDB | Database |
| Mongoose | ODM |
| JWT | Authentication |
| bcryptjs | Password Hashing |
| Multer | File Uploads |
| express-validator | Validation |

## 📦 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v18 or higher) - [Download](https://nodejs.org/)
- **MongoDB** (v6.0 or higher) - [Download](https://www.mongodb.com/try/download/community)
- **MongoDB Compass** (Optional, for GUI) - [Download](https://www.mongodb.com/try/download/compass)
- **Git** - [Download](https://git-scm.com/)

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/aswin32156/job_board_system.git
   cd job_board_system/job-portal
   ```

2. **Install dependencies**
   ```bash
   # Install root dependencies
   npm install

   # Install backend dependencies
   cd backend
   npm install

   # Install frontend dependencies
   cd ../frontend
   npm install
   ```

   Or use the shortcut:
   ```bash
   npm run install:all
   ```

## ⚙️ Configuration

1. **Create environment file for backend**
   
   Create a `.env` file in the `backend` directory:
   ```env
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/jobportal
   JWT_SECRET=your_super_secret_jwt_key_here
   NODE_ENV=development
   ```

2. **Start MongoDB**
   
   Make sure MongoDB is running on your system:
   ```bash
   # Windows (if installed as service)
   net start MongoDB

   # Or start manually
   mongod
   ```

## 🏃 Running the Application

### Development Mode

**Option 1: Run both servers together**
```bash
npm run dev
```

**Option 2: Run servers separately**
```bash
# Terminal 1 - Backend
cd backend
npm run dev

# Terminal 2 - Frontend
cd frontend
npm run dev
```

**Option 3: Use the batch file (Windows)**
```bash
# Double-click start-servers.bat
```

### Access the Application
- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:5000/api
- **API Health Check**: http://localhost:5000/api/health

## 📁 Project Structure

```
job-portal/
├── backend/
│   ├── src/
│   │   ├── config/
│   │   │   └── mongodb.js         # Database connection
│   │   ├── middleware/
│   │   │   ├── auth.js            # JWT authentication
│   │   │   └── upload.js          # File upload config
│   │   ├── models/
│   │   │   ├── User.js            # User model
│   │   │   ├── Job.js             # Job model
│   │   │   ├── Application.js     # Application model
│   │   │   ├── CandidateProfile.js
│   │   │   ├── EmployerProfile.js
│   │   │   ├── SavedJob.js
│   │   │   ├── Notification.js
│   │   │   └── JobReport.js
│   │   ├── routes/
│   │   │   ├── auth.js            # Authentication routes
│   │   │   ├── jobs.js            # Job routes
│   │   │   ├── employer.js        # Employer routes
│   │   │   ├── candidate.js       # Candidate routes
│   │   │   ├── notifications.js   # Notification routes
│   │   │   └── analytics.js       # Analytics routes
│   │   └── server.js              # Express server
│   ├── uploads/                   # Uploaded files
│   │   ├── resumes/
│   │   ├── logos/
│   │   └── profiles/
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── common/            # Reusable components
│   │   │   ├── jobs/              # Job-related components
│   │   │   └── layout/            # Layout components
│   │   ├── context/
│   │   │   └── AuthContext.jsx    # Authentication context
│   │   ├── pages/
│   │   │   ├── auth/              # Authentication pages
│   │   │   ├── candidate/         # Candidate pages
│   │   │   ├── employer/          # Employer pages
│   │   │   ├── Home.jsx
│   │   │   ├── Jobs.jsx
│   │   │   └── JobDetails.jsx
│   │   ├── services/
│   │   │   └── api.js             # API service
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── index.html
│   ├── tailwind.config.js
│   ├── vite.config.js
│   └── package.json
│
├── start-servers.bat              # Windows startup script
├── package.json                   # Root package.json
└── README.md
```

## 🔗 API Endpoints

### Authentication
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register/employer` | Register employer |
| POST | `/api/auth/register/candidate` | Register candidate |
| POST | `/api/auth/login` | Login user |
| GET | `/api/auth/me` | Get current user |
| GET | `/api/auth/verify/:token` | Verify email |

### Jobs
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/jobs` | Get all jobs (with filters) |
| GET | `/api/jobs/:id` | Get job by ID |
| POST | `/api/jobs` | Create job (Employer) |
| PUT | `/api/jobs/:id` | Update job (Employer) |
| DELETE | `/api/jobs/:id` | Delete job (Employer) |

### Candidate
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/candidate/dashboard` | Get dashboard data |
| GET | `/api/candidate/profile` | Get profile |
| PUT | `/api/candidate/profile` | Update profile |
| POST | `/api/candidate/resume` | Upload resume |
| POST | `/api/candidate/apply/:jobId` | Apply to job |
| GET | `/api/candidate/applications` | Get applications |
| POST | `/api/candidate/saved-jobs/:jobId` | Save job |
| GET | `/api/candidate/saved-jobs` | Get saved jobs |

### Employer
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/employer/dashboard` | Get dashboard data |
| GET | `/api/employer/jobs` | Get employer's jobs |
| GET | `/api/employer/jobs/:id/applications` | Get job applicants |
| PUT | `/api/employer/applications/:id/status` | Update application status |
| PUT | `/api/employer/profile` | Update company profile |
| POST | `/api/employer/logo` | Upload company logo |

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Aswin** - [GitHub](https://github.com/aswin32156)

---

<p align="center">
  Made with ❤️ for job seekers and employers
</p>
