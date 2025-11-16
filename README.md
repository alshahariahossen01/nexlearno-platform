# 🎓 NexLearno - Modern E-Learning Platform

[![Status](https://img.shields.io/badge/Status-Production%20Ready-success)](https://github.com)
[![Version](https://img.shields.io/badge/Version-2.0.0-blue)](https://github.com)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

> Transform your future with world-class online courses. Learn from industry experts at your own pace.

---

## 🌟 Features

### Core Functionality
- ✅ **Course Management** - Browse, search, and enroll in courses
- ✅ **User Authentication** - Secure sign-in/sign-up with session management
- ✅ **Learning Dashboard** - Track progress and manage enrollments
- ✅ **Interactive Lessons** - Video content with transcripts and notes
- ✅ **Progress Tracking** - Real-time course completion tracking
- ✅ **Certificates** - Generate certificates upon course completion
- ✅ **User Profiles** - Manage account settings and preferences

### Advanced Features
- 🤖 **AI Chat Assistant** - Get instant help while learning
- 📱 **Responsive Design** - Works on all devices (mobile, tablet, desktop)
- 🎨 **Modern UI/UX** - Beautiful interface with animations
- ♿ **Accessibility** - WCAG 2.1 AA compliant
- 🔒 **Security** - Rate limiting, input validation, secure sessions
- 🚀 **Performance** - Lazy loading, caching, optimized assets
- 🌐 **SEO Optimized** - Better search engine visibility

---

## 🚀 Quick Start

### Prerequisites
```bash
- Web Browser (Chrome, Firefox, Edge, Safari)
- Local Server (Live Server, Python HTTP Server, or similar)
- Node.js 14+ (optional, for backend features)
```

### Installation

**1. Clone the Repository**
```bash
git clone https://github.com/yourusername/nexlearno.git
cd nexlearno
```

**2. Open with Live Server**
```bash
# Option 1: VS Code Live Server Extension
# Right-click on index.html → "Open with Live Server"

# Option 2: Python HTTP Server
python -m http.server 5504

# Option 3: Node.js http-server
npx http-server -p 5504
```

**3. Access the Application**
```
Open browser: http://localhost:5504
```

### Optional: Backend Setup

For full features including API and database:

```bash
# Navigate to backend
cd backend

# Install dependencies
npm install

# Start server
npm start

# Backend runs on http://localhost:3000
```

---

## 📁 Project Structure

```
NexLearno/
├── index.html                 # Homepage
├── pages/                     # Application pages
│   ├── auth-signin.html      # Sign-in page
│   ├── auth-signup.html      # Sign-up page
│   ├── browse.html           # Course catalog
│   ├── course-detail.html    # Course details
│   ├── lesson.html           # Lesson viewer
│   ├── my-learning.html      # User dashboard
│   ├── profile.html          # User profile
│   ├── certificates.html     # Certificates
│   └── ...                   # Other pages
├── js/                        # JavaScript modules
│   ├── app.js                # Main application
│   ├── auth-service.js       # Authentication
│   ├── data.js               # Data fetching
│   ├── logger.js             # Production logger
│   ├── nav-helper.js         # Navigation helper
│   └── ...                   # Other modules
├── css/                       # Stylesheets
│   ├── base.css              # Base styles
│   ├── components.css        # Component styles
│   ├── responsive.css        # Responsive design
│   └── ...                   # Other styles
├── data/                      # Course data
│   ├── courses-enhanced.json # Enhanced course catalog
│   ├── courses.json          # Basic course catalog
│   └── lessons/              # Lesson data
├── backend/                   # Optional backend
│   ├── server.js             # Express server
│   ├── database.sqlite       # SQLite database
│   └── package.json          # Dependencies
├── docs/                      # Documentation
├── tests/                     # Test files
└── README.md                 # This file
```

---

## 💻 Usage

### For Users

**1. Create an Account**
- Go to: `http://localhost:5504/pages/auth-signup.html`
- Fill in your details
- Click "Sign Up"

**2. Browse Courses**
- Visit: `http://localhost:5504/pages/browse.html`
- Use filters to find courses
- Click "View Course" for details

**3. Enroll in a Course**
- On course page, click "Enroll Now"
- Course appears in "My Learning"

**4. Start Learning**
- Go to "My Learning" dashboard
- Click "Continue Learning" on any course
- Watch videos, take notes, complete lessons

**5. Get Certificate**
- Complete all lessons (100% progress)
- Visit "Certificates" page
- Download your certificate

### For Developers

**Adding a New Course**
```javascript
// Edit data/courses-enhanced.json
{
  "id": "new-course-id",
  "title": "New Course Title",
  "description": "Course description",
  "category": "Development",
  "level": "Beginner",
  "instructor": "Instructor Name",
  "duration": "10 hours",
  "price": 99.99,
  "thumbnail": "path/to/image.jpg",
  "curriculum": [
    {
      "week": 1,
      "title": "Week 1: Introduction",
      "lessons": [
        {
          "id": "lesson-1",
          "title": "Lesson 1",
          "duration": "15 min",
          "type": "video"
        }
      ]
    }
  ]
}
```

**Using the Logger**
```javascript
// Import logger
import logger from './js/logger.js';

// Development: Shows all logs
logger.log('Regular log');
logger.info('✅ Success message');
logger.warn('⚠️ Warning');
logger.error('❌ Error');

// Production (auto-detected): 
// Only errors/warns show, no debug/log/info
```

**Authentication Integration**
```javascript
// Import auth service
import authService from './js/auth-service.js';

// Check if user is logged in
if (authService.isAuthenticated()) {
  const user = authService.getCurrentUser();
  console.log('Welcome,', user.name);
}

// Sign in
await authService.signIn(email, password, rememberMe);

// Sign out
authService.logout();
```

**Navigation Helper (Consistent Avatar)**
```javascript
// Import nav helper
import { setupNavigation } from './js/nav-helper.js';

// Setup navigation with avatar
setupNavigation(); // Call once on page load

// Avatar automatically shows:
// - User initial in circle
// - Dropdown with profile links
// - Sign out option
```

---

## 🔧 Configuration

### Environment Detection
The application automatically detects the environment:
- **Development**: `localhost` → All logs enabled
- **Production**: Other domains → Only errors/warnings

### Manual Configuration
Edit `js/logger.js` to change environment:
```javascript
// Force production mode
logger.setEnvironment('production');

// Force development mode
logger.setEnvironment('development');
```

### API Endpoints
If using backend, update endpoints in `js/api-service.js`:
```javascript
const API_BASE_URL = 'http://localhost:3000/api';
// Change to your production URL when deploying
```

---

## 🧪 Testing

### Manual Testing

**Test Course Enrollment Flow:**
```bash
1. Sign in: http://localhost:5504/pages/auth-signin.html
2. Browse: http://localhost:5504/pages/browse.html
3. Select course: Click "View Course"
4. Enroll: Click "Enroll Now"
5. My Learning: http://localhost:5504/pages/my-learning.html
6. Start: Click "Continue Learning"
```

### Automated Tests

```bash
# Install Playwright
npm install

# Run tests
npm test

# Run specific test
npx playwright test tests/specs/course-enrollment.spec.ts
```

---

## 🎨 Customization

### Change Theme Colors
Edit `css/theme.css`:
```css
:root {
  --primary-color: #6366f1;    /* Change to your brand color */
  --secondary-color: #8b5cf6;  /* Secondary brand color */
  --accent-color: #ec4899;     /* Accent color */
}
```

### Change Logo
Replace `img/logo.svg` with your logo (keep same filename or update references).

### Add New Pages
```html
<!-- Create new page in pages/ directory -->
<!DOCTYPE html>
<html lang="en">
<head>
    <title>New Page - NexLearno</title>
    <link rel="stylesheet" href="../css/base.css">
</head>
<body>
    <!-- Your content -->
    <script type="module" src="../js/app.js"></script>
</body>
</html>
```

---

## 📊 Performance

### Load Times (Target)
- **First Contentful Paint**: < 1.5s
- **Time to Interactive**: < 3.5s
- **Largest Contentful Paint**: < 2.5s

### Optimizations Applied
- ✅ Lazy loading for images and videos
- ✅ CSS/JS minification (in production build)
- ✅ Caching strategies
- ✅ Code splitting
- ✅ Resource prefetching
- ✅ Gzip compression

---

## 🔒 Security

### Implemented Measures
- ✅ **Session Management**: Secure token-based authentication
- ✅ **Input Validation**: All user inputs sanitized
- ✅ **Rate Limiting**: Prevent brute force attacks
- ✅ **XSS Protection**: Output escaping
- ✅ **CSRF Protection**: Token validation
- ✅ **Secure Storage**: Encrypted localStorage
- ✅ **HTTPS Ready**: Works with SSL certificates

### Security Best Practices
```javascript
// Never store sensitive data in localStorage
// Use secure session tokens
// Validate all inputs on client AND server
// Implement rate limiting for auth endpoints
// Use HTTPS in production
```

---

## 🌐 Browser Support

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | 90+ | ✅ Full Support |
| Firefox | 88+ | ✅ Full Support |
| Safari | 14+ | ✅ Full Support |
| Edge | 90+ | ✅ Full Support |
| Opera | 76+ | ✅ Full Support |
| IE 11 | - | ❌ Not Supported |

---

## 🐛 Troubleshooting

### Common Issues

**Issue: Page not loading**
```bash
Solution: Check if server is running on correct port (5504)
```

**Issue: Courses not displaying**
```bash
Solution: Verify data/courses-enhanced.json exists and is valid JSON
```

**Issue: Authentication not working**
```bash
Solution: Clear browser localStorage and try again
# Open DevTools → Application → Local Storage → Clear
```

**Issue: Styles not applying**
```bash
Solution: Hard refresh browser (Ctrl+Shift+R or Cmd+Shift+R)
```

### Debug Mode

Enable debug logging:
```javascript
// Open browser console and run:
localStorage.setItem('elx:v1:debug_mode', 'true');
location.reload();

// Disable debug mode:
localStorage.setItem('elx:v1:debug_mode', 'false');
location.reload();
```

---

## 📚 Documentation

Additional documentation available in `/docs`:
- `SETUP.md` - Detailed setup instructions
- `ARCHITECTURE.md` - Technical architecture
- `DATA_MODELS.md` - Data structure reference
- `TESTING.md` - Testing guide
- `ACCESSIBILITY.md` - Accessibility guidelines

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Commit your changes** (`git commit -m 'Add amazing feature'`)
4. **Push to the branch** (`git push origin feature/amazing-feature`)
5. **Open a Pull Request**

### Code Standards
- Use ESLint for JavaScript linting
- Follow existing code style
- Add comments for complex logic
- Write meaningful commit messages
- Test your changes thoroughly

---

## 📝 Changelog

### Version 2.0.0 (2025-11-16)
- ✅ Added production-ready logger
- ✅ Implemented consistent avatar system
- ✅ Enhanced authentication service
- ✅ Improved course detail page design
- ✅ Added navigation helper module
- ✅ Cleaned up project structure
- ✅ Updated documentation

### Version 1.5.0 (Previous)
- Initial release with core features
- Basic authentication
- Course catalog
- Lesson viewer
- Progress tracking

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👥 Authors

**NexLearno Team**
- Lead Developer: Senior Developer (20+ years experience)
- UI/UX Designer: [Your Name]
- Content Creator: [Your Name]

---

## 🌟 Acknowledgments

- Bootstrap for UI components
- Font Awesome for icons
- AOS (Animate On Scroll) for animations
- SQLite for local database
- Express.js for backend
- Playwright for testing

---

## 📞 Support

Need help? Contact us:

- 📧 Email: support@nexlearno.com
- 💬 Discord: [Join our community](https://discord.gg/nexlearno)
- 🐦 Twitter: [@nexlearno](https://twitter.com/nexlearno)
- 📝 Issues: [GitHub Issues](https://github.com/yourusername/nexlearno/issues)

---

## 🗺️ Roadmap

### Q1 2026
- [ ] Mobile apps (iOS/Android)
- [ ] Live streaming classes
- [ ] Group discussions
- [ ] Advanced analytics

### Q2 2026
- [ ] Gamification features
- [ ] Social learning
- [ ] Marketplace for instructors
- [ ] Multi-language support

### Q3 2026
- [ ] AI-powered recommendations
- [ ] Adaptive learning paths
- [ ] Integration with LMS platforms
- [ ] Advanced certificates (blockchain)

---

## 💡 Tips for Success

1. **Start with Setup** - Follow SETUP.md for detailed instructions
2. **Use the Logger** - Helps debug issues in development
3. **Check Browser Console** - Errors appear here
4. **Test on Multiple Devices** - Ensure responsive design works
5. **Read the Documentation** - We've documented everything!

---

## ⚡ Quick Links

- [🏠 Homepage](http://localhost:5504/)
- [📚 Browse Courses](http://localhost:5504/pages/browse.html)
- [📝 Sign In](http://localhost:5504/pages/auth-signin.html)
- [👤 Profile](http://localhost:5504/pages/profile.html)
- [🎓 My Learning](http://localhost:5504/pages/my-learning.html)
- [📜 Certificates](http://localhost:5504/pages/certificates.html)

---

## 🎉 Thank You!

Thank you for using NexLearno! We're committed to providing the best online learning experience.

**Happy Learning! 🚀**

---

<div align="center">
  <strong>Built with ❤️ by the NexLearno Team</strong>
  <br>
  <sub>© 2025 NexLearno. All rights reserved.</sub>
</div>
