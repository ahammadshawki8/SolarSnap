# SolarSnap - Solar Panel Inspection System

A comprehensive solar farm inspection solution combining thermal imaging, computer vision, and cloud-based analytics for professional solar panel fault detection and maintenance management.

## 🎯 Project Overview

SolarSnap is a complete end-to-end system designed for solar farm operators and maintenance teams to efficiently inspect, document, and manage solar panel health using FLIR thermal cameras and mobile technology.

### Key Components

- **Frontend**: Android mobile app with FLIR ACE thermal camera integration
- **Backend**: Flask REST API with cloud sync and data management
- **Analytics**: Comprehensive reporting and fault analysis system

## 🚀 Quick Start

### Prerequisites

- **Java 21 (JDK 21)** - Required for Android/FLIR SDK compilation
- **Python 3.8+** - Required for backend API
- **Android Studio** (optional) - For mobile development
- **FLIR ACE Thermal Camera** - For thermal imaging capabilities

### Installation

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd SolarSnap
   ```

2. **Setup Backend**
   ```bash
   cd Backend
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   # or
   venv\Scripts\activate     # Windows
   pip install -r requirements.txt
   python init_db.py
   python run.py
   ```

3. **Setup Frontend**
   ```bash
   cd Frontend
   ./gradlew assembleDebug
   ./gradlew installDebug
   ```

## 📱 System Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Android App   │◄──►│   Flask API     │◄──►│   Database      │
│   (Frontend)    │    │   (Backend)     │    │   (SQLite/PG)   │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│  FLIR Thermal   │    │  File Storage   │    │   Analytics     │
│    Camera       │    │   (Images)      │    │   (Reports)     │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

## ✨ Key Features

### 🔥 Thermal Inspection
- Real-time thermal imaging with FLIR ACE cameras
- Automatic hotspot detection and temperature measurement
- Visual and thermal image capture with GPS coordinates
- Panel-by-panel inspection workflow

### 🗺️ Site Management
- Interactive solar farm mapping
- Panel layout visualization (up to 1,200+ panels)
- Fault location tracking and visualization
- Progress monitoring and completion status

### 📊 Analytics & Reporting
- Comprehensive fault analysis and trending
- Temperature distribution analytics
- Maintenance scheduling and recommendations
- Export capabilities (PDF, CSV, Excel)

### ☁️ Cloud Sync
- Offline-first mobile operation
- Automatic cloud synchronization
- Multi-user collaboration
- Secure data backup and recovery

### 🔐 Enterprise Security
- JWT-based authentication
- Role-based access control
- Company-level data isolation
- Secure API endpoints

## 📂 Project Structure

```
SolarSnap/
├── Frontend/                    # Android mobile application
│   ├── app/src/main/java/      # Java source code
│   ├── app/src/main/res/       # Android resources
│   ├── build.gradle.kts        # Android build configuration
│   └── README.md               # Frontend documentation
├── Backend/                     # Flask REST API
│   ├── app/                    # Python application code
│   │   ├── models/             # Database models
│   │   └── routes/             # API endpoints
│   ├── requirements.txt        # Python dependencies
│   ├── run.py                  # Application entry point
│   └── README.md               # Backend documentation
├── atlas-java-sdk-android-2.17.0/  # FLIR SDK libraries
└── README.md                   # This file
```

## 🛠️ Technology Stack

### Frontend (Android)
- **Language**: Java
- **SDK**: Android SDK 33+ (Target 36)
- **Thermal**: FLIR Atlas SDK 2.17.0
- **Camera**: CameraX, ML Kit Barcode Scanning
- **Location**: Google Location Services
- **UI**: Material Design with ACE-optimized components

### Backend (API)
- **Language**: Python 3.8+
- **Framework**: Flask with Flask-RESTful
- **Database**: SQLite (dev) / PostgreSQL (prod)
- **Authentication**: JWT with Flask-JWT-Extended
- **File Storage**: Local filesystem / Cloud storage
- **Deployment**: Gunicorn, Docker-ready

### Infrastructure
- **Database**: SQLite, PostgreSQL
- **Storage**: Local files, AWS S3 compatible
- **Deployment**: Render, Heroku, Docker
- **Monitoring**: Flask logging, error tracking

## 📈 Development Status

| Component | Status | Progress |
|-----------|--------|----------|
| Frontend UI | ✅ Complete | 100% |
| FLIR SDK Integration | 🔄 In Progress | 60% |
| Backend API | ✅ Complete | 100% |
| Database Schema | ✅ Complete | 100% |
| Authentication | ✅ Complete | 100% |
| File Upload | ✅ Complete | 100% |
| Cloud Sync | ✅ Complete | 100% |
| Reporting | ✅ Complete | 100% |
| **Overall** | **🔄 Beta** | **85%** |

## 🎯 Use Cases

### Solar Farm Operators
- Schedule and track routine inspections
- Monitor panel health and performance
- Generate maintenance reports
- Track fault resolution progress

### Field Technicians
- Conduct thermal inspections with mobile devices
- Document faults with thermal and visual evidence
- Work offline in remote locations
- Sync data when connectivity is available

### Maintenance Teams
- Prioritize repairs based on fault severity
- Access historical inspection data
- Generate work orders and reports
- Track maintenance completion

### Management
- Monitor inspection progress across multiple sites
- Analyze fault trends and patterns
- Generate executive reports
- Plan maintenance budgets and schedules

## 🔧 Configuration

### Environment Variables

Create `.env` files in both Frontend and Backend directories:

**Backend/.env**
```env
SECRET_KEY=your-secret-key
DATABASE_URL=sqlite:///solarsnap.db
JWT_SECRET_KEY=your-jwt-secret
UPLOAD_FOLDER=uploads
```

**Frontend Configuration**
- Configure API endpoints in `app/src/main/java/com/solarsnap/app/config/`
- Set FLIR SDK paths in `build.gradle.kts`
- Configure permissions in `AndroidManifest.xml`

## 🚀 Deployment

### Backend Deployment (Render/Heroku)
```bash
cd Backend
# Set environment variables in platform dashboard
# Deploy using Git integration or CLI
```

### Frontend Deployment (APK Distribution)
```bash
cd Frontend
./gradlew assembleRelease
# Distribute APK or publish to internal app store
```

## 🧪 Testing

### Backend Testing
```bash
cd Backend
python -m pytest tests/
```

### Frontend Testing
```bash
cd Frontend
./gradlew test
./gradlew connectedAndroidTest
```

## 📚 Documentation

- [Frontend README](Frontend/README.md) - Android app setup and development
- [Backend README](Backend/README.md) - API documentation and deployment
- [API Documentation](Backend/SolarSnap_API.postman_collection.json) - Postman collection

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

Proprietary - FLIR App Challenge 2025

## 🆘 Support

For technical support or questions:
- Check the component-specific README files
- Review the API documentation
- Contact the development team

---

**Built for**: Professional Solar Farm Inspection  
**Platform**: Android + Cloud API  
**Status**: Production Ready Beta  
**Last Updated**: March 2026