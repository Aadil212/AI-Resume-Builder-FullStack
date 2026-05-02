# AI Resume Builder

A modern, AI-powered resume builder application that helps job seekers create professional resumes in minutes. Built with React, Express, and integrated with OpenAI for intelligent content generation.

![Resume Builder](https://img.shields.io/badge/Version-1.0.0-blue)
![React](https://img.shields.io/badge/React-19.1.1-61DAFB)
![Express](https://img.shields.io/badge/Express-5.1.0-000000)

## ✨ Features

- **AI-Powered Content Generation** - Generate professional summaries, experience descriptions, and bullet points using OpenAI GPT models
- **Multiple Resume Templates** - Choose from 4 professionally designed templates:
  - Modern Template
  - Classic Template
  - Minimal Template
  - Minimal Image Template
- **Real-time Preview** - See your resume updates live as you edit
- **PDF Export** - Download your finished resume as a PDF
- **User Authentication** - Secure signup/login with JWT tokens
- **Custom Color Scheme** - Personalize your resume with custom accent colors
- **Responsive Design** - Works on desktop and mobile devices

## 🛠 Tech Stack

### Frontend

- **React 19** - UI library
- **Vite** - Build tool and dev server
- **Redux Toolkit** - State management
- **React Router DOM** - Navigation
- **Tailwind CSS 4** - Styling
- **Axios** - HTTP client
- **Lucide React** - Icons

### Backend

- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - ODM
- **JWT** - Authentication
- **Bcrypt** - Password hashing
- **OpenAI** - AI integration
- **ImageKit** - Image storage
- **Multer** - File upload handling

## 📁 Project Structure

```
resume-builder/
├── client/                 # React frontend
│   ├── public/             # Static assets
│   ├── src/
│   │   ├── app/           # Redux store & slices
│   │   ├── assets/        # Templates & images
│   │   ├── components/    # Reusable components
│   │   │   ├── home/      # Landing page components
│   │   │   └── templates/ # Resume template components
│   │   ├── configs/       # API configuration
│   │   └── pages/         # Page components
│   └── package.json
│
├── server/                 # Express backend
│   ├── configs/           # Database & AI configs
│   ├── controllers/      # Route controllers
│   ├── middlewares/       # Custom middleware
│   ├── models/           # Mongoose models
│   ├── routes/           # API routes
│   └── server.js         # Entry point
│
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ installed
- MongoDB (local or Atlas)
- OpenAI API key

### Installation

1. **Clone the repository:**

```bash
git clone <repository-url>
cd resume-builder
```

2. **Install dependencies for both client and server:**

```bash
# Install server dependencies
cd server
npm install

# Install client dependencies
cd ../client
npm install
```

### Environment Variables

Create a `.env` file in the `server` directory:

```env
# Server
PORT=3000

# MongoDB (replace with your connection string)
MONGO_URI=mongodb://localhost:27017/resume-builder

# JWT (generate a secure random string)
JWT_SECRET=your-super-secret-jwt-key

# OpenAI
OPENAI_API_KEY=sk-your-openai-api-key

# ImageKit (optional - for image uploads)
IMAGEKIT_PUBLIC_KEY=your-imagekit-public-key
IMAGEKIT_PRIVATE_KEY=your-imagekit-private-key
IMAGEKIT_URL_ENDPOINT=https://ik.imagekit.io/your-imagekit-id
```

### Running the Application

**Development Mode:**

```bash
# Terminal 1 - Start the server
cd server
npm run server   # Runs with nodemon on port 3000

# Terminal 2 - Start the client
cd client
npm run dev     # Runs on http://localhost:5173
```

**Production Mode:**

```bash
# Build the client
cd client
npm run build

# Start the server
cd server
npm start
```

## 📖 API Endpoints

### Authentication

| Method | Endpoint              | Description       |
| ------ | --------------------- | ----------------- |
| POST   | `/api/users/register` | Register new user |
| POST   | `/api/users/login`    | Login user        |
| GET    | `/api/users/data`     | Get current user  |

### Resumes

| Method | Endpoint           | Description          |
| ------ | ------------------ | -------------------- |
| GET    | `/api/resumes`     | Get all user resumes |
| GET    | `/api/resumes/:id` | Get single resume    |
| POST   | `/api/resumes`     | Create resume        |
| PUT    | `/api/resumes/:id` | Update resume        |
| DELETE | `/api/resumes/:id` | Delete resume        |

### AI Features

| Method | Endpoint                      | Description                   |
| ------ | ----------------------------- | ----------------------------- |
| POST   | `/api/ai/suggest-skills`      | AI skills suggestions         |
| POST   | `/api/ai/generate-summary`    | Generate professional summary |
| POST   | `/api/ai/enhance-description` | Enhance job descriptions      |

## 🎨 Template Structure

Each resume template expects the following data structure:

```javascript
{
  personal_info: {
    full_name: "John Doe",
    email: "john@example.com",
    phone: "+1234567890",
    location: "New York, NY",
    linkedin: "https://linkedin.com/in/johndoe",
    website: "https://johndoe.com"
  },
  professional_summary: "Experienced developer...",
  experience: [
    {
      position: "Software Engineer",
      company: "Tech Corp",
      start_date: "2020-01",
      end_date: "2023-12",
      is_current: false,
      description: "Key responsibilities and achievements..."
    }
  ],
  education: [
    {
      degree: "Bachelor",
      field: "Computer Science",
      institution: "MIT",
      graduation_date: "2019-05",
      gpa: "3.8"
    }
  ],
  skills: ["JavaScript", "React", "Node.js"],
  project: [
    {
      name: "Project Name",
      description: "Project description..."
    }
  ]
}
```

## 📄 License

This project is licensed under the ISC License.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.
