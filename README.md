# Notes Management App

A full-stack notes management application built with the MERN stack (MongoDB, Express.js, React, Node.js). Features include user authentication, CRUD operations for notes, tagging system, search functionality, and a modern responsive UI.

## 🚀 Features

### Backend Features
- **User Authentication**: JWT-based registration and login
- **Notes CRUD**: Create, read, update, and delete notes
- **Tagging System**: Add and filter notes by tags
- **Search Functionality**: Full-text search across note titles and content
- **Note Management**: Pin, archive, and organize notes
- **Security**: Rate limiting, input validation, and secure headers
- **Error Handling**: Comprehensive error handling and logging

### Frontend Features
- **Modern UI**: Clean, responsive design with Tailwind CSS
- **Real-time Search**: Instant search with debounced input
- **Note Editor**: Rich text editing with auto-save
- **Color Coding**: Customizable note colors
- **Tag Management**: Easy tag creation and filtering
- **Mobile Responsive**: Optimized for all device sizes
- **Dark Mode Ready**: Prepared for theme switching

## 🛠️ Tech Stack

### Backend
- **Node.js**: Runtime environment
- **Express.js**: Web framework
- **MongoDB**: Database with Mongoose ODM
- **JWT**: Authentication tokens
- **bcryptjs**: Password hashing
- **Helmet**: Security middleware
- **CORS**: Cross-origin resource sharing
- **Rate Limiting**: API protection

### Frontend
- **React 18**: UI library with hooks
- **Vite**: Build tool and dev server
- **React Router**: Client-side routing
- **Tailwind CSS**: Utility-first CSS framework
- **Axios**: HTTP client
- **React Hot Toast**: Toast notifications
- **Lucide React**: Modern icon library
- **Context API**: State management

## 📁 Project Structure

```
notes-app/
├── backend/
│   ├── config/
│   │   └── database.js          # MongoDB connection
│   ├── controllers/
│   │   ├── authController.js    # Authentication logic
│   │   └── notesController.js   # Notes CRUD logic
│   ├── middleware/
│   │   ├── auth.js              # JWT authentication middleware
│   │   ├── errorHandler.js      # Global error handler
│   │   └── validation.js        # Input validation middleware
│   ├── models/
│   │   ├── User.js              # User schema
│   │   ├── Note.js              # Note schema
│   │   └── index.js             # Model exports
│   ├── routes/
│   │   ├── auth.js              # Authentication routes
│   │   └── notes.js             # Notes routes
│   ├── utils/
│   │   ├── constants.js         # App constants
│   │   └── helpers.js           # Utility functions
│   ├── .env.example             # Environment variables template
│   ├── .gitignore
│   ├── package.json
│   └── server.js                # Entry point
├── frontend/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── Header.jsx       # App header with search
│   │   │   ├── Layout.jsx       # Main layout wrapper
│   │   │   ├── LoadingSpinner.jsx
│   │   │   ├── ProtectedRoute.jsx
│   │   │   ├── PublicRoute.jsx
│   │   │   └── Sidebar.jsx      # Navigation sidebar
│   │   ├── context/
│   │   │   ├── AuthContext.jsx  # Authentication state
│   │   │   └── NotesContext.jsx # Notes state management
│   │   ├── pages/
│   │   │   ├── Dashboard.jsx    # Notes dashboard
│   │   │   ├── Login.jsx        # Login page
│   │   │   ├── NoteEditor.jsx   # Note creation/editing
│   │   │   ├── NotFound.jsx     # 404 page
│   │   │   ├── Profile.jsx      # User profile settings
│   │   │   └── Register.jsx     # Registration page
│   │   ├── services/
│   │   │   ├── api.js           # Axios configuration
│   │   │   ├── localStorage.js  # Local storage utilities
│   │   │   └── validation.js    # Form validation
│   │   ├── utils/
│   │   │   ├── constants.js     # Frontend constants
│   │   │   ├── helpers.js       # Utility functions
│   │   │   └── hooks.js         # Custom React hooks
│   │   ├── App.jsx
│   │   ├── index.css           # Tailwind styles
│   │   └── main.jsx
│   ├── .env.example
│   ├── .gitignore
│   ├── package.json
│   ├── postcss.config.js
│   ├── tailwind.config.js
│   └── vite.config.js
└── README.md
```

## 🚀 Quick Start

### Prerequisites
- Node.js (v18 or higher)
- MongoDB Atlas account or local MongoDB installation
- Git

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd notes-app/backend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   ```bash
   cp .env.example .env
   ```

   Update `.env` with your values:
   ```env
   MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/notes-app
   JWT_SECRET=your-super-secret-jwt-key-minimum-32-characters
   JWT_EXPIRE=7d
   PORT=5000
   NODE_ENV=development
   CLIENT_URL=http://localhost:5173
   ```

4. **Start the server**
   ```bash
   # Development
   npm run dev

   # Production
   npm start
   ```

   Server will run on `http://localhost:5000`

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd ../frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Environment Setup**
   ```bash
   cp .env.example .env
   ```

   Update `.env`:
   ```env
   VITE_API_BASE_URL=http://localhost:5000/api
   VITE_APP_NAME=Notes App
   VITE_APP_VERSION=1.0.0
   ```

4. **Start the development server**
   ```bash
   npm run dev
   ```

   Frontend will run on `http://localhost:5173`

## 🌐 Deployment

### Backend Deployment (Render)

1. **Create a new Web Service on Render**
2. **Connect your GitHub repository**
3. **Configure the service:**
   - **Build Command**: `npm install`
   - **Start Command**: `npm start`
   - **Environment**: Node.js
   - **Root Directory**: `backend`

4. **Set environment variables:**
   ```
   MONGO_URI=mongodb+srv://...
   JWT_SECRET=your-production-jwt-secret
   JWT_EXPIRE=7d
   NODE_ENV=production
   CLIENT_URL=https://your-frontend-domain.vercel.app
   PORT=5000
   ```

### Frontend Deployment (Vercel)

1. **Install Vercel CLI**
   ```bash
   npm i -g vercel
   ```

2. **Deploy from frontend directory**
   ```bash
   cd frontend
   vercel
   ```

3. **Set environment variables in Vercel dashboard:**
   ```
   VITE_API_BASE_URL=https://your-backend-domain.render.com/api
   VITE_APP_NAME=Notes App
   VITE_APP_VERSION=1.0.0
   ```

### Database Setup (MongoDB Atlas)

1. **Create a MongoDB Atlas account**
2. **Create a new cluster**
3. **Create a database user**
4. **Whitelist your IP address (or use 0.0.0.0/0 for all)**
5. **Get your connection string**
6. **Update the `MONGO_URI` in your environment variables**

## 📡 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user
- `PUT /api/auth/profile` - Update profile
- `PUT /api/auth/change-password` - Change password
- `DELETE /api/auth/account` - Delete account

### Notes
- `GET /api/notes` - Get all notes (with filters)
- `GET /api/notes/:id` - Get single note
- `POST /api/notes` - Create new note
- `PUT /api/notes/:id` - Update note
- `DELETE /api/notes/:id` - Delete note
- `GET /api/notes/tags` - Get all tags
- `GET /api/notes/search` - Search notes
- `POST /api/notes/bulk` - Bulk operations

## 🔧 Environment Variables

### Backend (.env)
```env
# Database
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/notes-app

# JWT
JWT_SECRET=your-super-secret-jwt-key-minimum-32-characters
JWT_EXPIRE=7d

# Server
PORT=5000
NODE_ENV=development

# CORS
CLIENT_URL=http://localhost:5173

# Rate Limiting
RATE_LIMIT_WINDOW_MS=900000
RATE_LIMIT_MAX_REQUESTS=100
```

### Frontend (.env)
```env
# API
VITE_API_BASE_URL=http://localhost:5000/api

# App
VITE_APP_NAME=Notes App
VITE_APP_VERSION=1.0.0

# Environment
VITE_NODE_ENV=development
```

## 🧪 Available Scripts

### Backend
```bash
npm start          # Start production server
npm run dev        # Start development server with nodemon
```

### Frontend
```bash
npm run dev        # Start development server
npm run build      # Build for production
npm run preview    # Preview production build
npm run lint       # Run ESLint
```

## 🔐 Security Features

- **JWT Authentication**: Secure token-based authentication
- **Password Hashing**: bcryptjs with salt rounds
- **Rate Limiting**: Prevents API abuse
- **CORS Protection**: Configured for specific origins
- **Input Validation**: Comprehensive validation middleware
- **Security Headers**: Helmet.js for security headers
- **Error Handling**: No sensitive data in error responses

## 🎨 UI Features

- **Responsive Design**: Mobile-first approach
- **Dark Mode Ready**: Theme system prepared
- **Loading States**: Skeleton loaders and spinners
- **Error Boundaries**: Graceful error handling
- **Toast Notifications**: User feedback system
- **Keyboard Shortcuts**: Power user features
- **Infinite Scroll**: Efficient note loading
- **Search Highlighting**: Visual search results

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🐛 Known Issues

- [ ] Rich text editor not implemented
- [ ] File attachments not supported
- [ ] Collaborative editing not available
- [ ] Offline mode not implemented

## 🔮 Future Enhancements

- [ ] Rich text editor with formatting
- [ ] File attachments and images
- [ ] Note sharing and collaboration
- [ ] Export notes (PDF, Markdown)
- [ ] Voice notes and transcription
- [ ] AI-powered note suggestions
- [ ] Advanced search with filters
- [ ] Note templates
- [ ] Backup and sync features
- [ ] Mobile app (React Native)

## 💡 Tips

- Use keyboard shortcuts for faster navigation
- Pin important notes for quick access
- Use tags to organize notes by category
- Archive old notes to keep your dashboard clean
- Use the search feature to quickly find notes
- Change note colors for visual organization

## 📧 Support

If you encounter any issues or have questions, please:

1. Check the existing issues on GitHub
2. Create a new issue with detailed information
3. Provide error logs and steps to reproduce

## 🙏 Acknowledgments

- React team for the amazing library
- Tailwind CSS for the utility-first CSS framework
- MongoDB for the flexible database
- Vercel and Render for hosting platforms
- All open-source contributors

---

**Happy note-taking! 📝✨**
