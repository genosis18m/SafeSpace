# SafeSpace - Your Complete Mental Health Companion

![SafeSpace Logo](https://via.placeholder.com/

SafeSpace is a comprehensive mental health platform designed to provide 24/7 support, AI-powered counseling, mood tracking, and community connection. Built with modern web technologies, SafeSpace offers a complete toolkit for mental wellness management in a secure, user-friendly environment.

## ✨ Key Features

### 🧠 AI-Powered Mental Health Counselor
- **24/7 Availability**: Get instant support and guidance whenever you need it
- **Evidence-Based Responses**: AI trained on mental health best practices
- **Personalized Conversations**: Tailored advice based on your specific situation
- **Crisis Recognition**: Immediate escalation to professional help when needed

### 📊 Advanced Mood Tracking
- **Daily Check-ins**: Simple mood logging with emoji-based interface
- **Activity Correlation**: Track how activities influence your emotional state
- **Trend Analysis**: Visualize your mental health journey over time
- **Insights & Recommendations**: Personalized suggestions based on your patterns

### 👥 Supportive Community
- **Discussion Forums**: Connect with others on similar mental health journeys
- **Discord Integration**: Real-time chat support with moderated channels
- **Anonymous Sharing**: Safe space to share experiences and receive support
- **Peer Support Groups**: Specialized communities for different mental health topics

### 🚨 Crisis Intervention
- **Immediate Response**: Priority support with response times under 8 minutes
- **Global Hotlines**: Access to crisis hotlines worldwide
- **Safety Planning**: Tools to create personalized crisis response plans
- **Emergency Contacts**: Quick access to local emergency services

### 📈 Progress Tracking
- **Visual Analytics**: Charts and graphs showing your wellness journey
- **Goal Setting**: Customizable mental health objectives
- **Achievement System**: Gamified progress with milestones and rewards
- **Data Export**: Download your progress reports for healthcare providers

### 📚 Educational Resources
- **Curated Content**: Evidence-based articles and guides
- **Video Library**: Educational content on mental health topics
- **Self-Help Tools**: Interactive exercises and coping strategies
- **Professional Insights**: Content reviewed by licensed therapists

## 🏗️ Architecture

SafeSpace is built as a modern monorepo using the following technology stack:

### Frontend
- **React 18** with TypeScript for type-safe development
- **Vite** for fast development and optimized builds
- **Tailwind CSS** for responsive, beautiful UI design
- **Framer Motion** for smooth animations and transitions
- **Recharts** for data visualization and analytics
- **React Router** for seamless navigation

### Backend
- **Node.js** with Express for robust API development
- **TypeScript** for enhanced code quality and maintainability
- **JWT Authentication** for secure user sessions
- **CORS** enabled for cross-origin requests

### Database
- **PostgreSQL** for reliable data persistence
- **Prisma ORM** for type-safe database operations
- **Automated Migrations** for seamless schema updates

### Infrastructure
- **Docker** containerization for consistent deployment
- **Docker Compose** for orchestrating services
- **Environment-based Configuration** for different deployment stages

## 🚀 Quick Start

### Prerequisites
- Node.js 18+ 
- Docker and Docker Compose
- PostgreSQL (or use Docker)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-org/safespace.git
   cd safespace
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   # Root directory
   cp .env.example .env
   
   # API
   cp apps/api/.env.example apps/api/.env
   
   # Frontend
   cp apps/frontend/.env.example apps/frontend/.env
   ```

4. **Generate Prisma client**
   ```bash
   npx prisma generate --schema=packages/db/prisma/schema.prisma
   ```

5. **Start with Docker**
   ```bash
   docker compose up --build
   ```

6. **Run database migrations**
   ```bash
   docker compose exec api npx prisma migrate deploy --schema=packages/db/prisma/schema.prisma
   ```

### Access the Application
- **Frontend**: http://localhost:3000
- **API**: http://localhost:3001
- **Database**: PostgreSQL on port 5432

## 📁 Project Structure

```
SafeSpace/
├── apps/
│   ├── api/                    # Backend Express API
│   │   ├── src/
│   │   │   ├── routes/         # API route handlers
│   │   │   ├── middleware/     # Authentication & validation
│   │   │   └── index.ts        # Server entry point
│   │   └── Dockerfile
│   ├── frontend/               # React frontend application
│   │   ├── src/
│   │   │   ├── components/     # Reusable UI components
│   │   │   ├── pages/          # Application pages
│   │   │   └── main.tsx        # App entry point
│   │   └── Dockerfile
│   └── docs/                   # Documentation site
├── packages/
│   ├── db/                     # Database schema & client
│   │   ├── prisma/
│   │   │   ├── schema.prisma   # Database schema
│   │   │   └── migrations/     # Database migrations
│   │   └── client.ts           # Prisma client configuration
│   ├── ui/                     # Shared UI components
│   ├── eslint-config/          # Shared ESLint configurations
│   └── typescript-config/      # Shared TypeScript configurations
├── docker-compose.yml          # Multi-service orchestration
├── turbo.json                  # Turborepo configuration
└── package.json                # Root package configuration
```

## 🔧 Development

### Available Scripts

```bash
# Development
npm run dev              # Start all services in development mode
npm run build           # Build all applications
npm run lint            # Run ESLint across all packages
npm run check-types     # TypeScript type checking

# Database
npx prisma studio       # Open Prisma Studio (database GUI)
npx prisma migrate dev  # Create and apply new migration
npx prisma generate     # Regenerate Prisma client
```

### Environment Variables

#### Backend API (apps/api/.env)
```env
DATABASE_URL=postgres://safespace:safespace@db:5432/safespace
JWT_SECRET=your-secure-jwt-secret
PORT=3001
```

#### Frontend (apps/frontend/.env)
```env
VITE_API_URL=http://localhost:3001
```

#### Database (packages/db/.env)
```env
DATABASE_URL=postgres://safespace:safespace@localhost:5432/safespace
```

## 🔒 Security Features

- **Data Encryption**: All sensitive data encrypted at rest and in transit
- **HIPAA Compliance**: Follows healthcare data protection standards
- **JWT Authentication**: Secure token-based authentication
- **Rate Limiting**: API protection against abuse
- **Input Validation**: Comprehensive data sanitization
- **Privacy Controls**: User-configurable privacy settings

## 📱 Mobile Support

SafeSpace is fully responsive and provides an excellent mobile experience:
- **Progressive Web App (PWA)** capabilities
- **Touch-optimized** interface
- **Offline functionality** for basic features
- **Push notifications** for reminders and alerts

## 🌍 Accessibility

- **WCAG 2.1 AA Compliant** design
- **Screen reader** compatible
- **Keyboard navigation** support
- **High contrast** mode available
- **Multiple language** support (coming soon)

## 🔗 API Documentation

### Authentication Endpoints
- `POST /api/auth/login` - User authentication
- `POST /api/auth/register` - New user registration
- `POST /api/auth/logout` - User logout

### Mood Tracking Endpoints
- `GET /api/mood` - Retrieve mood entries
- `POST /api/mood` - Create new mood entry
- `PUT /api/mood/:id` - Update mood entry
- `DELETE /api/mood/:id` - Delete mood entry

### User Management Endpoints
- `GET /api/user/profile` - Get user profile
- `PUT /api/user/profile` - Update user profile
- `DELETE /api/user/account` - Delete user account

## 🧪 Testing

```bash
# Run all tests
npm test

# Run tests for specific package
npm test --workspace=apps/api
npm test --workspace=apps/frontend

# Run tests in watch mode
npm test --watch
```

## 📦 Deployment

### Docker Production Deployment

1. **Build production images**
   ```bash
   docker compose -f docker-compose.prod.yml build
   ```

2. **Deploy to production**
   ```bash
   docker compose -f docker-compose.prod.yml up -d
   ```

### Cloud Deployment Options

- **Vercel** - Frontend deployment
- **Railway** - Full-stack deployment
- **AWS ECS** - Container orchestration
- **Google Cloud Run** - Serverless containers
- **DigitalOcean App Platform** - Managed deployment

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Workflow

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Code Standards

- **TypeScript** for all new code
- **ESLint** and **Prettier** for code formatting
- **Conventional Commits** for commit messages
- **Tests required** for new features

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

### Crisis Support
If you're experiencing a mental health crisis:
- **US**: Call 988 (Suicide & Crisis Lifeline)
- **UK**: Call 116 123 (Samaritans)
- **Emergency**: Call your local emergency number

### Technical Support
- **GitHub Issues**: [Report bugs or request features](https://github.com/your-org/safespace/issues)
- **Discord Community**: [Join our developer community](https://discord.gg/safespace)
- **Email**: support@safespace.app

## 🙏 Acknowledgments

- Mental health professionals who provided guidance
- Open source communities for excellent tools and libraries
- Beta testers who provided valuable feedback
- Contributors who help make SafeSpace better

## 🔮 Roadmap

### Upcoming Features
- [ ] **Mobile Apps** - Native iOS and Android applications
- [ ] **Telehealth Integration** - Video calls with licensed therapists
- [ ] **Wearable Integration** - Apple Watch and Fitbit mood tracking
- [ ] **AI Insights** - Advanced analytics and personalized recommendations
- [ ] **Family Accounts** - Shared dashboards for family mental health
- [ ] **Multilingual Support** - Additional language options

### Long-term Goals
- [ ] **Research Partnerships** - Collaborate with mental health research institutions
- [ ] **Enterprise Solutions** - Workplace mental health programs
- [ ] **Healthcare Integration** - Electronic health record compatibility
- [ ] **Global Expansion** - Localized crisis support worldwide

---
