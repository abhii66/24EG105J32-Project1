# 📝 MyBlog — Full Stack Blog Application

A full-stack blog platform built with the MERN stack, featuring role-based access for Users, Authors, and Admins.

---

## 🚀 Features

### 👤 User
- Register and login with JWT-based authentication
- Browse and read articles on the home feed
- Comment on articles
- View author profiles

### ✍️ Author
- Write, edit, and delete articles
- Manage article status (active/deleted)
- View own articles dashboard

### 🛡️ Admin
- View all users and authors
- Block or activate user accounts
- Manage platform content

### 🌐 General
- Cloudinary image uploads for profile pictures
- Cookie-based authentication with HTTP-only tokens
- Protected routes based on user role
- Responsive, mobile-friendly UI

---

## 🛠️ Tech Stack

### Frontend
- React (Vite)
- React Router v7
- Zustand (global state management)
- Axios
- React Hook Form
- React Hot Toast
- Tailwind CSS

### Backend
- Node.js
- Express.js
- MongoDB + Mongoose
- JWT (jsonwebtoken)
- bcryptjs
- Cloudinary
- Multer
- Cookie Parser

---

## 📁 Project Structure

```
Blog-App/
├── Blog-Frontend/
│   └── blog-app/
│       ├── src/
│       │   ├── components/
│       │   │   ├── Header.jsx
│       │   │   ├── Footer.jsx
│       │   │   ├── Home.jsx
│       │   │   ├── Login.jsx
│       │   │   ├── Register.jsx
│       │   │   ├── UserProfile.jsx
│       │   │   ├── AuthorProfile.jsx
│       │   │   ├── AuthorArticles.jsx
│       │   │   ├── WriteArticles.jsx
│       │   │   ├── EditArticle.jsx
│       │   │   ├── ArticleByID.jsx
│       │   │   ├── AdminProfile.jsx
│       │   │   ├── UserList.jsx
│       │   │   ├── AuthorList.jsx
│       │   │   ├── ProtectedRoute.jsx
│       │   │   └── Unauthorized.jsx
│       │   ├── store/
│       │   │   └── authStore.js
│       │   ├── styles/
│       │   │   └── common.js
│       │   └── App.jsx
│       └── package.json
│
└── Blog-Backend/
    ├── APIs/
    │   ├── CommonAPI.js
    │   ├── UserAPI.js
    │   ├── AuthorAPI.js
    │   └── AdminAPI.js
    ├── models/
    │   ├── UserModel.js
    │   └── ArticleModel.js
    ├── middlewares/
    │   └── verifyToken.js
    ├── config/
    │   ├── cloudinary.js
    │   ├── cloudinaryUpload.js
    │   └── multer.js
    ├── server.js
    └── package.json
```

---

## ⚙️ Getting Started

### Prerequisites
- Node.js v18+
- MongoDB (local or Atlas)
- Cloudinary account

### Backend Setup

```bash
cd Blog-Backend
npm install
```

Create a `.env` file in `Blog-Backend/`:

```env
PORT=6677
DB_URL=mongodb://localhost:27017/blogapp
SECRET_KEY=your_jwt_secret
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

Start the server:

```bash
node server.js
# or with nodemon
nodemon server.js
```

### Frontend Setup

```bash
cd Blog-Frontend/blog-app
npm install
npm run dev
```

---

## 🔐 API Routes

### Common (`/common-api`)
| Method | Route | Description |
|--------|-------|-------------|
| POST | `/users` | Register user |
| POST | `/users/login` | Login |
| GET | `/users/logout` | Logout |
| GET | `/check-auth` | Verify session |

### User (`/user-api`)
| Method | Route | Description |
|--------|-------|-------------|
| GET | `/articles` | Get all active articles |
| GET | `/article/:id` | Get article by ID |
| PUT | `/articles` | Add comment to article |

### Author (`/author-api`)
| Method | Route | Description |
|--------|-------|-------------|
| POST | `/articles` | Create new article |
| GET | `/articles` | Get own articles |
| PUT | `/articles` | Edit article |
| PATCH | `/articles` | Toggle article status |
| PATCH | `/articles/:id/status` | Delete/restore article |
| DELETE | `/articles/:articleId/comments/:commentId` | Delete comment |

### Admin (`/admin-api`)
| Method | Route | Description |
|--------|-------|-------------|
| GET | `/users/user` | Get all users |
| GET | `/users/author` | Get all authors |
| GET | `/articles/article` | Get all articles |
| PATCH | `/users` | Block/activate user |
| PATCH | `/articles` | Block/activate article |

---

## 👥 User Roles

| Role | Access |
|------|--------|
| `USER` | Read articles, comment |
| `AUTHOR` | Write, edit, delete own articles |
| `ADMIN` | Manage all users and content |

---

## 🌍 Deployment

- **Frontend**: Vercel
- **Backend**: Render
- **Database**: MongoDB Atlas
- **Images**: Cloudinary

---

## 🧑‍💻 Author

Built by **Abhishekar Reddy** as a full-stack learning project.
