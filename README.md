# 🔐 VERA - Verify Every Real Asset

<div align="center">

![VERA Logo](frontend/public/images/logo.png)

**Unlimited Authenticity. Real People. Real Stories.**

[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg)](https://opensource.org/licenses/ISC)
[![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)](https://nodejs.org/)
[![Next.js](https://img.shields.io/badge/Next.js-15+-black.svg)](https://nextjs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-green.svg)](https://www.mongodb.com/atlas)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-orange.svg)](https://openai.com/)

</div>

## 🌟 Overview

VERA is a cutting-edge **authentic content verification platform** that leverages AI-powered deepfake detection and blockchain security to protect against manipulated media. In an era where deepfakes and AI-generated content are becoming increasingly sophisticated, VERA provides users with the tools to verify the authenticity of their content and protect their digital identity.

### 🎯 Mission Statement

> "To create a world where digital authenticity is not just possible, but simple, fast, and reliable."

## ✨ Key Features

### 🤖 AI-Powered Detection

- **Advanced Deepfake Detection**: OpenAI GPT-4 powered analysis of images, videos, audio, and text
- **Multi-Modal Support**: Comprehensive analysis across all media types
- **Real-time Processing**: Fast, accurate detection with detailed reasoning
- **Confidence Scoring**: Probability-based authenticity assessment

### 🔗 Blockchain Integration

- **Wallet Authentication**: Secure login via MetaMask, Coinbase, and WalletConnect
- **Immutable Records**: Content verification stored on blockchain
- **Decentralized Security**: No single point of failure
- **Transparent Verification**: Public verification records

### 📱 Modern Web Application

- **Responsive Design**: Beautiful, modern UI built with Next.js 15
- **Real-time Updates**: Live content verification and status updates
- **Media Management**: Comprehensive library for verified content
- **User Profiles**: Personalized experience with content history

### 🛡️ Security & Privacy

- **End-to-End Encryption**: Secure data transmission and storage
- **Privacy-First**: User data protection and minimal data collection
- **Rate Limiting**: Protection against abuse and spam
- **Input Validation**: Comprehensive security measures

## 🏗️ Architecture

### Frontend (Next.js 15)

```
frontend/
├── src/
│   ├── app/                 # App Router pages
│   │   ├── create-tag/      # Content creation
│   │   ├── explore/         # Content discovery
│   │   ├── login/           # Authentication
│   │   ├── profile/         # User management
│   │   └── tag/[id]/        # Content viewing
│   ├── components/          # Reusable UI components
│   │   ├── custom/          # Application-specific components
│   │   └── ui/              # Base UI components
│   ├── context/             # React context providers
│   └── lib/                 # Utilities and configuration
```

### Backend (Node.js + Express)

```
backend/
├── detection/               # AI detection module
│   ├── controllers/         # Business logic
│   ├── utils/              # AI and media utilities
│   └── middleware/         # Upload handling
├── user/                   # User management
├── tag/                    # Content management
├── watermark/              # Watermarking utilities
└── config/                 # Database and service configs
```

## 🚀 Quick Start

### Prerequisites

- **Node.js** 18+ and npm
- **MongoDB** (local or Atlas)
- **OpenAI API Key** (for AI detection)
- **Cloudinary Account** (for media storage)
- **Web3 Wallet** (MetaMask, Coinbase, etc.)

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-username/vera.git
   cd vera
   ```

2. **Install dependencies**

   ```bash
   # Backend
   cd backend
   npm install

   # Frontend
   cd ../frontend
   npm install
   ```

3. **Environment Setup**

   **Backend (.env)**

   ```env
   PORT=5000
   NODE_ENV=development
   MONGODB_URI=mongodb://localhost:27017/vera
   OPENAI_API_KEY=your_openai_api_key
   CLOUDINARY_CLOUD_NAME=your_cloudinary_name
   CLOUDINARY_API_KEY=your_cloudinary_key
   CLOUDINARY_API_SECRET=your_cloudinary_secret
   CORS_ORIGIN=http://localhost:3000
   ```

   **Frontend (.env.local)**

   ```env
   NEXT_PUBLIC_API_URL=http://localhost:5000
   NEXT_PUBLIC_APP_URL=http://localhost:3000
   ```

4. **Start the application**

   ```bash
   # Terminal 1 - Backend
   cd backend
   npm run dev

   # Terminal 2 - Frontend
   cd frontend
   npm run dev
   ```

5. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000

## 📖 Usage Guide

### 🔐 Getting Started

1. **Connect Your Wallet**

   - Click "Get Started" on the welcome screen
   - Connect using MetaMask, Coinbase, or WalletConnect
   - Your wallet address becomes your unique identifier

2. **Create Your First Tag**

   - Navigate to "Create Tag" from the main dashboard
   - Upload an image, video, or audio file
   - Add a description and category
   - Submit for AI verification

3. **View Verification Results**
   - AI analysis provides authenticity probability
   - Detailed reasoning explains the assessment
   - Content is stored securely with blockchain verification

### 🎨 Content Management

- **Media Library**: View all your verified content
- **Categories**: Organize content by type and topic
- **Search & Filter**: Find specific content quickly
- **Sharing**: Share verified content with confidence

### 🔍 Verification Process

1. **Upload**: Submit media for analysis
2. **AI Analysis**: OpenAI processes the content
3. **Blockchain Storage**: Verification record stored immutably
4. **Results**: Receive detailed authenticity report

## 🛠️ API Documentation

### Detection Endpoints

#### `POST /api/detect`

Analyze content for authenticity

**Request:**

```bash
curl -X POST http://localhost:5000/api/detect \
  -F "file_data=@image.jpg"
```

**Response:**

```json
{
  "media_type": "image",
  "deepfake_probability": 15,
  "natural_probability": 85,
  "reasoning": {
    "content_analysis": "High-quality portrait photograph",
    "deepfake_indicators": "No obvious signs of manipulation",
    "authentic_indicators": "Natural skin texture, consistent lighting",
    "overall": "Image appears to be authentic"
  },
  "cloudinary_url": "https://res.cloudinary.com/...",
  "provided_source": "uploaded file"
}
```

#### `GET /api/detect/health`

Check detection service status

#### `GET /api/detect/supported-types`

Get supported file types and limits

### User Management

- `GET /api/users` - Get all users
- `POST /api/users` - Create new user
- `GET /api/users/:id` - Get user by ID
- `PUT /api/users/:id` - Update user
- `DELETE /api/users/:id` - Delete user

### Content Management

- `GET /api/tags` - Get all tags
- `POST /api/tags` - Create new tag
- `GET /api/tags/:id` - Get tag by ID
- `PUT /api/tags/:id` - Update tag
- `DELETE /api/tags/:id` - Delete tag

## 🔧 Configuration

### Supported Media Types

**Images:** JPG, JPEG, PNG, GIF, WebP, BMP, SVG  
**Videos:** MP4, MOV, AVI, MKV, WebM, FLV  
**Audio:** MP3, WAV, OGG, AAC, FLAC, M4A  
**Documents:** PDF, TXT

### File Limits

- **Maximum file size**: 100MB
- **Maximum files per request**: 5
- **Supported formats**: See media types above

### Environment Variables

| Variable                | Description                     | Required |
| ----------------------- | ------------------------------- | -------- |
| `MONGODB_URI`           | MongoDB connection string       | ✅       |
| `OPENAI_API_KEY`        | OpenAI API key for AI detection | ✅       |
| `CLOUDINARY_CLOUD_NAME` | Cloudinary cloud name           | ✅       |
| `CLOUDINARY_API_KEY`    | Cloudinary API key              | ✅       |
| `CLOUDINARY_API_SECRET` | Cloudinary API secret           | ✅       |
| `PORT`                  | Server port (default: 5000)     | ❌       |
| `NODE_ENV`              | Environment mode                | ❌       |
| `CORS_ORIGIN`           | Allowed CORS origin             | ❌       |

## 🧪 Testing

### Health Checks

```bash
# Backend health
curl http://localhost:5000/health

# Detection service health
curl http://localhost:5000/api/detect/health
```

### File Upload Test

```bash
curl -X POST http://localhost:5000/api/detect \
  -F "file_data=@test-image.jpg"
```

### Supported Types Check

```bash
curl http://localhost:5000/api/detect/supported-types
```

## 🚀 Deployment

### Frontend (Vercel)

```bash
cd frontend
npm run build
# Deploy to Vercel or your preferred platform
```

### Backend (Railway/Heroku)

```bash
cd backend
# Configure production environment variables
npm start
```

### Environment Setup

- Set production environment variables
- Configure MongoDB Atlas for production
- Set up Cloudinary for media storage
- Configure OpenAI API for production usage

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

### Development Setup

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

### Code Style

- Use ESLint and Prettier for code formatting
- Follow TypeScript best practices
- Write meaningful commit messages
- Add JSDoc comments for functions

## 📄 License

This project is licensed under the ISC License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **OpenAI** for providing the AI detection capabilities
- **Cloudinary** for media storage and optimization
- **Next.js** team for the amazing React framework
- **MongoDB** for the database solution
- **Ethers.js** for Web3 integration

## 📞 Support

- **Documentation**: [Wiki](https://github.com/your-username/vera/wiki)
- **Issues**: [GitHub Issues](https://github.com/your-username/vera/issues)
- **Discussions**: [GitHub Discussions](https://github.com/your-username/vera/discussions)
- **Email**: support@vera-app.com

## 🔮 Roadmap

### Phase 1 (Current)

- ✅ Basic AI detection
- ✅ Web3 authentication
- ✅ Content management
- ✅ User profiles

### Phase 2 (Coming Soon)

- 🔄 Advanced search and discovery
- 🔄 Community features
- 🔄 Mobile application
- 🔄 API rate limiting improvements

### Phase 3 (Future)

- 📋 Multi-chain support
- 📋 Advanced analytics
- 📋 Enterprise features
- 📋 White-label solutions

---

<div align="center">

**Built with ❤️ by the VERA Team**

[Website](https://vera-app.com) • [Documentation](https://docs.vera-app.com) • [Community](https://discord.gg/vera)

</div>
# VERA-master
