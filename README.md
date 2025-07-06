# 🔓 VulnLab - MERN Stack Application

A deliberately vulnerable web application built with the MERN stack (MongoDB, Express.js, React, Node.js) for educational purposes. This modern application demonstrates common vulnerabilities in contemporary web applications and APIs.

## ⚠️ Security Warning

**This application contains intentional security vulnerabilities and should NEVER be deployed in a production environment or on systems connected to sensitive networks.**

## 🎯 Purpose

This application serves as a practice platform for:
- Modern web application security testing
- API security testing
- React/Node.js vulnerability assessment
- NoSQL injection techniques
- JWT security issues
- RESTful API penetration testing

## 🛠️ Technologies Used

- **Frontend**: React 18+, React Router, Axios, Material-UI
- **Backend**: Node.js 16+, Express.js 4+, JWT, bcrypt
- **Database**: MongoDB 5.0+, Mongoose ODM
- **Additional**: Redis (for session storage), Multer (file uploads)

## 📋 Prerequisites

Before running this application, ensure you have the following installed:

- **Node.js** 16.x or higher
- **npm** 8.x or higher (or **yarn** 1.22+)
- **MongoDB** 5.0+ (Community Edition)
- **Redis** 6.x+ (optional, for session storage)
- **Git** (for cloning the repository)

## 🚀 Installation & Setup

### Quick Start (Development Mode)

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/vulnlab-mern.git
   cd vulnlab-mern
   ```

2. **Install Dependencies**
   ```bash
   # Install backend dependencies
   npm install
   
   # Install frontend dependencies
   cd client
   npm install
   cd ..
   ```

3. **Setup Environment Variables**
   ```bash
   # Copy environment templates
   cp .env.example .env
   cp client/.env.example client/.env
   
   # Edit the .env files with your configuration
   ```

4. **Start MongoDB**
   ```bash
   # Ubuntu/Debian
   sudo systemctl start mongod
   
   # macOS (using Homebrew)
   brew services start mongodb-community
   
   # Windows
   net start MongoDB
   ```

5. **Setup Database**
   ```bash
   # Run database seeding script
   npm run seed
   ```

6. **Start the Application**
   ```bash
   # Development mode (runs both frontend and backend)
   npm run dev
   
   # Or start separately:
   # Backend: npm run server
   # Frontend: npm run client
   ```

7. **Access the Application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000
   - API Documentation: http://localhost:5000/api-docs

### Production Setup

1. **Environment Configuration**
   ```bash
   # Production environment variables
   NODE_ENV=production
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/vulnlab_prod
   JWT_SECRET=your-super-secret-key
   REDIS_URL=redis://localhost:6379
   ```

2. **Build and Deploy**
   ```bash
   # Build React application
   npm run build
   
   # Start production server
   npm start
   ```

## 📁 Project Structure

```
vulnlab-mern/
├── README.md
├── package.json
├── .env.example
├── .gitignore
├── server.js
├── client/
│   ├── package.json
│   ├── public/
│   │   ├── index.html
│   │   ├── favicon.ico
│   │   └── manifest.json
│   ├── src/
│   │   ├── components/
│   │   │   ├── common/
│   │   │   │   ├── Header.js
│   │   │   │   ├── Footer.js
│   │   │   │   └── Navigation.js
│   │   │   ├── auth/
│   │   │   │   ├── Login.js
│   │   │   │   ├── Register.js
│   │   │   │   └── Profile.js
│   │   │   └── vulnerabilities/
│   │   │       ├── XSS.js
│   │   │       ├── NoSQLi.js
│   │   │       ├── IDOR.js
│   │   │       └── FileUpload.js
│   │   ├── pages/
│   │   │   ├── Home.js
│   │   │   ├── Dashboard.js
│   │   │   └── VulnerabilityList.js
│   │   ├── services/
│   │   │   ├── api.js
│   │   │   ├── auth.js
│   │   │   └── storage.js
│   │   ├── hooks/
│   │   │   ├── useAuth.js
│   │   │   └── useLocalStorage.js
│   │   ├── context/
│   │   │   └── AuthContext.js
│   │   ├── utils/
│   │   │   ├── constants.js
│   │   │   └── helpers.js
│   │   ├── App.js
│   │   ├── App.css
│   │   └── index.js
│   ├── build/
│   └── .env.example
├── server/
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── userController.js
│   │   ├── commentController.js
│   │   └── uploadController.js
│   ├── models/
│   │   ├── User.js
│   │   ├── Comment.js
│   │   ├── Product.js
│   │   └── Upload.js
│   ├── routes/
│   │   ├── auth.js
│   │   ├── users.js
│   │   ├── comments.js
│   │   ├── products.js
│   │   └── uploads.js
│   ├── middleware/
│   │   ├── auth.js
│   │   ├── validation.js
│   │   ├── errorHandler.js
│   │   └── rateLimit.js
│   ├── config/
│   │   ├── database.js
│   │   ├── redis.js
│   │   └── cloudinary.js
│   ├── utils/
│   │   ├── jwt.js
│   │   ├── bcrypt.js
│   │   └── sanitize.js
│   └── seeds/
│       ├── users.js
│       ├── products.js
│       └── comments.js
├── uploads/
│   ├── images/
│   ├── documents/
│   └── temp/
├── logs/
│   ├── access.log
│   ├── error.log
│   └── security.log
├── tests/
│   ├── unit/
│   │   ├── controllers/
│   │   ├── models/
│   │   └── utils/
│   ├── integration/
│   │   ├── auth.test.js
│   │   ├── users.test.js
│   │   └── api.test.js
│   └── e2e/
│       ├── login.test.js
│       └── vulnerabilities.test.js
├── docs/
│   ├── API.md
│   ├── VULNERABILITIES.md
│   ├── DEPLOYMENT.md
│   └── CONTRIBUTING.md
├── scripts/
│   ├── setup.js
│   ├── seed.js
│   └── reset.js
├── docker-compose.yml
├── Dockerfile
└── .dockerignore
```

## 🎯 Available Vulnerabilities

### 1. Authentication & Authorization
- **JWT Vulnerabilities**: Weak secrets, algorithm confusion
- **Session Management**: Insecure session handling
- **IDOR**: Insecure Direct Object References
- **Privilege Escalation**: Role-based access control bypass

### 2. Injection Attacks
- **NoSQL Injection**: MongoDB injection techniques
- **XSS**: React XSS via dangerouslySetInnerHTML
- **Command Injection**: Server-side command execution
- **LDAP Injection**: Directory traversal attacks

### 3. API Security Issues
- **Mass Assignment**: Object property pollution
- **Rate Limiting**: API abuse scenarios
- **CORS Misconfiguration**: Cross-origin issues
- **GraphQL Vulnerabilities**: Query depth, introspection

### 4. File Upload Vulnerabilities
- **Unrestricted Upload**: Malicious file uploads
- **Path Traversal**: Directory traversal via uploads
- **MIME Type Bypass**: Content-type spoofing

### 5. Client-Side Vulnerabilities
- **XSS**: Cross-site scripting in React
- **CSRF**: Cross-site request forgery
- **DOM Clobbering**: HTML injection attacks
- **Prototype Pollution**: JavaScript object pollution

## 🔧 Configuration

### Environment Variables

**Backend (.env):**
```env
NODE_ENV=development
PORT=5000
MONGODB_URI=mongodb://localhost:27017/vulnlab
JWT_SECRET=your-jwt-secret-key
JWT_EXPIRE=7d
REDIS_URL=redis://localhost:6379
BCRYPT_ROUNDS=10
MAX_FILE_SIZE=10485760
CORS_ORIGIN=http://localhost:3000
```

**Frontend (client/.env):**
```env
REACT_APP_API_URL=http://localhost:5000
REACT_APP_ENABLE_LOGGING=true
REACT_APP_VERSION=1.0.0
GENERATE_SOURCEMAP=false
```

### Database Configuration

**MongoDB Connection:**
```javascript
const mongoose = require('mongoose');

mongoose.connect(process.env.MONGODB_URI, {
  useNewUrlParser: true,
  useUnifiedTopology: true,
});
```

**Redis Configuration:**
```javascript
const redis = require('redis');
const client = redis.createClient({
  url: process.env.REDIS_URL
});
```

## 🧪 Testing Guidelines

### API Testing

**Authentication Endpoints:**
```bash
# Register new user
curl -X POST http://localhost:5000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{"username":"testuser","email":"test@example.com","password":"password123"}'

# Login
curl -X POST http://localhost:5000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"test@example.com","password":"password123"}'
```

**NoSQL Injection Testing:**
```bash
# MongoDB injection in login
curl -X POST http://localhost:5000/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":{"$ne":""},"password":{"$ne":""}}'

# User enumeration
curl -X GET "http://localhost:5000/api/users?username[$ne]=admin"
```

**JWT Testing:**
```bash
# JWT with weak secret
curl -X GET http://localhost:5000/api/profile \
  -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
```

### Frontend Testing

**XSS Payloads:**
```javascript
// React XSS via dangerouslySetInnerHTML
<div dangerouslySetInnerHTML={{__html: userInput}} />

// Event handler injection
<img src="x" onerror="alert('XSS')" />
```

**CSRF Testing:**
```html
<form action="http://localhost:5000/api/profile" method="POST">
  <input type="hidden" name="email" value="attacker@evil.com">
  <input type="submit" value="Update Profile">
</form>
```

## 🛠️ Development Tools

### Available Scripts

```bash
# Development
npm run dev          # Start both client and server
npm run server       # Start backend only
npm run client       # Start frontend only

# Testing
npm test            # Run all tests
npm run test:unit   # Run unit tests
npm run test:e2e    # Run end-to-end tests
npm run test:api    # Run API tests

# Database
npm run seed        # Seed database with test data
npm run reset       # Reset database
npm run migrate     # Run database migrations

# Build & Deploy
npm run build       # Build production version
npm start          # Start production server
npm run analyze    # Analyze bundle size

# Code Quality
npm run lint       # ESLint check
npm run format     # Prettier formatting
npm run audit      # Security audit
```

### Docker Support

```bash
# Build and run with Docker
docker-compose up -d

# Individual services
docker-compose up mongodb redis
docker-compose up vulnlab-backend
docker-compose up vulnlab-frontend
```

## 📊 API Documentation

API documentation is available at `http://localhost:5000/api-docs` when running the server.

### Core Endpoints

```
Authentication:
POST /api/auth/register    # User registration
POST /api/auth/login       # User login
POST /api/auth/logout      # User logout
GET  /api/auth/profile     # Get user profile

Users:
GET    /api/users          # Get all users
GET    /api/users/:id      # Get user by ID
PUT    /api/users/:id      # Update user
DELETE /api/users/:id      # Delete user

Comments:
GET    /api/comments       # Get all comments
POST   /api/comments       # Create comment
PUT    /api/comments/:id   # Update comment
DELETE /api/comments/:id   # Delete comment

Products:
GET    /api/products       # Get all products
POST   /api/products       # Create product
PUT    /api/products/:id   # Update product
DELETE /api/products/:id   # Delete product

Uploads:
POST   /api/uploads        # Upload file
GET    /api/uploads/:id    # Get file
DELETE /api/uploads/:id    # Delete file
```

## 🚀 Deployment

### Local Development
```bash
npm run dev
```

### Production Deployment
```bash
# Build the application
npm run build

# Set production environment
export NODE_ENV=production

# Start the server
npm start
```

### Docker Deployment
```bash
# Using Docker Compose
docker-compose -f docker-compose.prod.yml up -d

# Using individual containers
docker build -t vulnlab-mern .
docker run -p 5000:5000 vulnlab-mern
```

## 🛡️ Security Considerations

This application demonstrates what NOT to do:
- ❌ Weak JWT secrets
- ❌ No input validation
- ❌ No rate limiting
- ❌ Insecure file uploads
- ❌ NoSQL injection vulnerabilities
- ❌ Missing authentication checks
- ❌ CORS misconfiguration
- ❌ Prototype pollution
- ❌ Mass assignment vulnerabilities

## 📚 Learning Resources

- [OWASP API Security Top 10](https://owasp.org/www-project-api-security/)
- [Node.js Security Guide](https://nodejs.org/en/docs/guides/security/)
- [React Security Best Practices](https://snyk.io/blog/10-react-security-best-practices/)
- [MongoDB Security](https://docs.mongodb.com/manual/security/)
- [JWT Security Best Practices](https://auth0.com/blog/a-look-at-the-latest-draft-for-jwt-bcp/)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-vulnerability`
3. Commit your changes: `git commit -am 'Add new vulnerability'`
4. Push to the branch: `git push origin feature/new-vulnerability`
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## ⚠️ Disclaimer

This application is for educational purposes only. The developers are not responsible for any misuse of this application. Always obtain proper authorization before testing on systems you do not own.

## 🐛 Known Issues

- Application is intentionally vulnerable
- No production-ready security measures
- Logging may contain sensitive information
- Error messages may reveal system information
- Database queries are intentionally unsafe

## 📞 Support

For questions or issues:
- Create an issue on GitHub
- Check the documentation in `/docs/`
- Review the API documentation
- Check the troubleshooting guide

---

**Remember: This is a vulnerable application by design. Use responsibly and only in controlled environments.**
