# StreamFlow

A robust, production-grade video hosting and streaming backend service built by ruthvik using Node.js, Express, MongoDB, Mongoose, JWT, and Cloudinary.

## Overview

StreamFlow provides a full-featured video platform backend:
- **Authentication & Authorization**: Secure registration, login, logout, password change, access tokens, refresh tokens, and cookie handling.
- **Video Management**: Video upload, publishing, thumbnail management, views, and duration tracking.
- **Engagement**: Comments, video likes, comment likes, tweet likes, subscriptions, and playlists.
- **Tweets / Community Posts**: Post updates, read user feeds, edit, and delete posts.
- **Channel Dashboard & Analytics**: Channel statistics, video metrics, subscriber counts, and total views.
- **Asset Storage**: Cloudinary integration for scalable video and image asset uploads with temporary Multer staging.

---

## Tech Stack

- **Runtime**: [Node.js](https://nodejs.org/)
- **Framework**: [Express.js](https://expressjs.com/)
- **Database**: [MongoDB](https://www.mongodb.com/) via [Mongoose](https://mongoosejs.com/)
- **Pagination**: `mongoose-aggregate-paginate-v2`
- **Security & Auth**: `jsonwebtoken`, `bcrypt`
- **File Uploads**: `multer`, `cloudinary`
- **Development**: `nodemon`, `prettier`

---

## Project Structure

```
StreamFlow/
├── public/
│   └── temp/             # Temporary storage for file uploads
├── src/
│   ├── controllers/      # Route controllers (user, video, like, comment, etc.)
│   ├── db/               # MongoDB connection setup
│   ├── middlewares/      # Auth, multer file upload middlewares
│   ├── models/           # Mongoose schemas & data models
│   ├── routes/           # Express API route definitions
│   ├── utils/            # ApiError, ApiResponse, asyncHandler, Cloudinary
│   ├── app.js            # Express app configuration & middleware
│   ├── constants.js      # App constants (DB name)
│   └── index.js          # App entry point
├── .env.sample           # Sample environment variables
├── .gitignore
├── .prettierrc
├── package.json
└── README.md
```

---

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- MongoDB instance (MongoDB Atlas or local MongoDB)
- [Cloudinary](https://cloudinary.com/) account for media hosting

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/ruthvik-papabattula/StreamFlow.git
   cd StreamFlow
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Configure Environment Variables:**
   Copy `.env.sample` to `.env`:
   ```bash
   cp .env.sample .env
   ```
   Fill in your configuration values:
   ```env
   PORT=8000
   MONGODB_URI=your_mongodb_connection_string
   CORS_ORIGIN=*
   ACCESS_TOKEN_SECRET=your_access_token_secret
   ACCESS_TOKEN_EXPIRY=1d
   REFRESH_TOKEN_SECRET=your_refresh_token_secret
   REFRESH_TOKEN_EXPIRY=10d
   CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
   CLOUDINARY_API_KEY=your_cloudinary_api_key
   CLOUDINARY_API_SECRET=your_cloudinary_api_secret
   ```

4. **Run the Development Server:**
   ```bash
   npm run dev
   ```

---

## API Routes

| Resource | Route | Description |
| :--- | :--- | :--- |
| **Healthcheck** | `/api/v1/healthcheck` | Health check endpoint |
| **Users** | `/api/v1/users` | Registration, login, logout, avatar/cover uploads, profile |
| **Videos** | `/api/v1/videos` | Video uploads, publish toggle, details, updates |
| **Comments** | `/api/v1/comments` | Video comments & replies |
| **Likes** | `/api/v1/likes` | Like/unlike videos, comments, tweets |
| **Playlists** | `/api/v1/playlist` | Create, update, add/remove videos from playlists |
| **Subscriptions** | `/api/v1/subscriptions` | Channel subscriptions and subscriber lists |
| **Tweets** | `/api/v1/tweets` | Community tweet posts |
| **Dashboard** | `/api/v1/dashboard` | Channel statistics and uploaded videos |

---

## Author

**ruthvik**  
- GitHub: [@ruthvik-papabattula](https://github.com/ruthvik-papabattula)

## License

ISC