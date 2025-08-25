# 🎓 StudentHub - Comprehensive Student Life Management Platform

A full-stack web application designed to connect students, universities, and companies in a unified ecosystem. Built with modern technologies including Next.js, GraphQL, Prisma, and PostgreSQL.

## 🌟 Features

### 🎯 Core Functionality
- **Multi-role Authentication System** - Students, Universities, Companies, and Admins
- **Event Management** - Create, discover, and participate in academic and professional events
- **Social Networking** - Posts, likes, saves, and user interactions
- **Real-time Notifications** - Push notifications and in-app alerts
- **Interactive Maps** - Location-based event discovery using Leaflet
- **File Management** - S3 integration for media uploads and storage

### 🏗️ Architecture
- **Frontend**: Next.js 15 with TypeScript and Tailwind CSS
- **Backend**: Node.js with Express and Apollo GraphQL Server
- **Database**: PostgreSQL (Prisma ORM) + MongoDB (hybrid approach)
- **Authentication**: JWT-based with role-based access control
- **Real-time**: WebSocket subscriptions for live updates
- **Cloud Services**: AWS S3 for file storage, FCM for push notifications

## 🚀 Tech Stack

### Frontend
- **Framework**: Next.js 15 (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS 4 + Radix UI Components
- **State Management**: Apollo Client for GraphQL
- **Maps**: Leaflet + React Leaflet
- **Forms**: React Hook Form
- **Theming**: Next-themes (dark/light mode)

### Backend
- **Runtime**: Node.js
- **Framework**: Express.js
- **GraphQL**: Apollo Server 4
- **Database ORM**: Prisma 6
- **Authentication**: JWT + bcrypt
- **File Upload**: AWS SDK v3
- **Notifications**: Firebase Cloud Messaging
- **Email**: SendGrid integration

### Database
- **Primary**: PostgreSQL with Prisma
- **Secondary**: MongoDB for specific features
- **Migrations**: Automated schema management

## 📁 Project Structure

```
StudetnHUb/
├── Hub-backend/                 # Backend API server
│   ├── src/
│   │   ├── config/             # Database and service configurations
│   │   ├── middlewares/        # Authentication and validation
│   │   ├── models/             # Data models and schemas
│   │   ├── resolvers/          # GraphQL resolvers
│   │   ├── schema/             # GraphQL type definitions
│   │   ├── services/           # External service integrations
│   │   └── utils/              # Helper functions
│   ├── prisma/                 # Database schema and migrations
│   └── Server.js               # Main server entry point
│
├── Hub-Frontend/               # Next.js frontend application
│   ├── app/                    # Next.js 15 app router
│   │   ├── auth/              # Authentication pages
│   │   ├── dashboard/         # Role-based dashboards
│   │   ├── events/            # Event management
│   │   ├── posts/             # Social posts
│   │   └── profile/           # User profiles
│   ├── components/             # Reusable UI components
│   │   ├── dashboard/         # Dashboard-specific components
│   │   ├── ui/                # Radix UI components
│   │   └── shared/            # Common components
│   ├── lib/                    # Utility functions and hooks
│   └── public/                 # Static assets
```

## 🛠️ Installation & Setup

### Prerequisites
- Node.js 18+ 
- PostgreSQL 14+
- MongoDB 5+
- AWS Account (for S3)
- Firebase Project (for FCM)

### Backend Setup

1. **Clone and install dependencies**
   ```bash
   cd Hub-backend
   npm install
   ```

2. **Environment Configuration**
   Create a `.env` file in the backend root:
   ```env
   DATABASE_URL="postgresql://username:password@localhost:5432/studenthub"
   MONGODB_URI="mongodb://localhost:27017/studenthub"
   JWT_SECRET="your-jwt-secret"
   AWS_ACCESS_KEY_ID="your-aws-key"
   AWS_SECRET_ACCESS_KEY="your-aws-secret"
   AWS_REGION="us-east-1"
   S3_BUCKET_NAME="your-s3-bucket"
   FCM_SERVER_KEY="your-fcm-key"
   SENDGRID_API_KEY="your-sendgrid-key"
   ```

3. **Database Setup**
   ```bash
   npx prisma migrate dev
   npx prisma generate
   ```

4. **Start Development Server**
   ```bash
   npm run dev
   ```

### Frontend Setup

1. **Install dependencies**
   ```bash
   cd Hub-Frontend
   npm install
   ```

2. **Environment Configuration**
   Create a `.env.local` file:
   ```env
   NEXT_PUBLIC_GRAPHQL_URL=http://localhost:4000/graphql
   NEXT_PUBLIC_S3_BUCKET=your-s3-bucket
   ```

3. **Start Development Server**
   ```bash
   npm run dev
   ```

## 🔐 Authentication & Roles

### User Roles
- **Student**: Access to events, posts, and networking features
- **University**: Create and manage academic events, student outreach
- **Company**: Post job opportunities, host professional events
- **Admin**: Platform management and user oversight

### Security Features
- JWT-based authentication
- Role-based access control (RBAC)
- Password hashing with bcrypt
- CORS protection
- Helmet.js security headers

## 📊 Database Schema

### Core Models
- **User**: Central user entity with role-specific relationships
- **Event**: Internal and external events with participation tracking
- **Post**: Social media-style posts with likes and saves
- **Notification**: Real-time user notifications
- **UserActivity**: User interaction tracking

### Key Features
- Hybrid PostgreSQL/MongoDB architecture
- Automated migrations with Prisma
- Optimized indexes for performance
- Referential integrity constraints

## 🚀 Deployment

### Backend Deployment
- **Environment**: Node.js production server
- **Database**: Managed PostgreSQL service
- **File Storage**: AWS S3
- **Process Manager**: PM2 or similar

### Frontend Deployment
- **Platform**: Vercel (recommended) or Netlify
- **Build**: `npm run build`
- **Environment**: Production environment variables

## 🔧 Development Commands

### Backend
```bash
npm run dev          # Start development server
npm run start        # Start production server
npm run migrate      # Run database migrations
npm run studio       # Open Prisma Studio
```

### Frontend
```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server
npm run lint         # Run ESLint
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

For support and questions:
- Create an issue in the GitHub repository
- Check the documentation in the `/docs` folder
- Review the GraphQL schema for API reference

## 🎯 Roadmap

- [ ] Mobile app development
- [ ] Advanced analytics dashboard
- [ ] AI-powered event recommendations
- [ ] Integration with university systems
- [ ] Enhanced notification system
- [ ] Multi-language support

---

**Built with ❤️ for the student community**
