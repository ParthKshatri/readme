
# 🚀 SpaceEx - Exoplanet Detection Platform

<div align="center">

**Advanced Machine Learning Platform for Astronomical Discovery**

[![React](https://img.shields.io/badge/React-18.2.0-61DAFB?logo=react)](https://reactjs.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.104.1-009688?logo=fastapi)](https://fastapi.tiangolo.com)
[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?logo=python)](https://python.org)
[![Machine Learning](https://img.shields.io/badge/ML-Dual%20Pipeline-FF6F00?logo=scikitlearn)](https://scikit-learn.org)

*Unveiling the secrets of distant worlds through cutting-edge AI*

[🚀 Live Demo](#) • [📚 Documentation](#) • [🐛 Report Bug](https://github.com/koffandaff/spaceex/issues) • [💡 Request Feature](https://github.com/koffandaff/spaceex/issues)

</div>

## 📖 Table of Contents
- [🌌 Project Overview](#-project-overview)
- [🛠 Tech Stack](#-tech-stack)
- [🚀 Features](#-features)
- [🏗️ System Architecture](#️-system-architecture)
- [📊 Machine Learning Pipeline](#-machine-learning-pipeline)
- [🔌 API Documentation](#-api-documentation)
- [🛠️ Installation & Setup](#️-installation--setup)
- [🎯 Usage Guide](#-usage-guide)
- [👥 Development Team](#-development-team)
- [🤝 Contributing](#-contributing)
- [🔮 Future Scope](#-future-scope)
- [📄 License](#-license)

---

## 🌌 Project Overview

SpaceEx is a sophisticated web application that leverages advanced machine learning algorithms to detect exoplanets from astronomical data. By analyzing light curve data from telescopes like Kepler and TESS, SpaceEx provides astronomers and researchers with a powerful tool for identifying potential exoplanets with unprecedented accuracy.

### 🎯 Project Vision
To democratize exoplanet discovery by providing an accessible, accurate, and scalable platform that combines state-of-the-art machine learning with intuitive visualization tools.

### 🔬 Scientific Significance
- **Automated Detection**: Reduces manual analysis time from weeks to minutes
- **Dual-Pipeline System**: Specialized models for KOI (Kepler) and K2 mission data
- **Multi-Model Consensus**: Combines predictions from specialized ML algorithms
- **Confidence Scoring**: Provides probabilistic assessments of discoveries
- **Visual Analytics**: Interactive visualizations for result interpretation

---

## 🛠 Tech Stack

### Frontend Layer
- **React 18** - Modern component-based UI framework
- **React Router DOM** - Client-side routing and navigation
- **CSS3** - Cyberpunk space-themed styling with animations
- **Context API** - State management for authentication and user data

### Backend Layer
- **FastAPI** - High-performance Python web framework with dual-pipeline support
- **Python 3.9+** - Core programming language
- **Uvicorn** - ASGI server for production deployment
- **Pydantic** - Data validation and settings management

### Machine Learning - Dual Pipeline System
- **KOI Pipeline** (Kepler Data): XGBoost (91.53% accuracy), GradientBoosting, StackingEnsemble
- **K2 Pipeline** (K2 Mission Data): ExtraTrees (89.72% accuracy), RandomForest, XGBoost
- **Scikit-learn** - Ensemble methods and preprocessing
- **Matplotlib** - Scientific visualization and plotting

### Data & Storage
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing and array operations
- **Joblib** - Model serialization and persistence

### Development & Deployment
- **Vite** - Frontend build tool and development server
- **npm** - JavaScript package management
- **pip** - Python dependency management
- **Git** - Version control and collaboration

---

## 🚀 Features

### 🌟 Core Capabilities
- **🤖 Dual-Pipeline ML System** - Specialized models for KOI and K2 astronomical data
- **📁 Multi-File Batch Processing** - Simultaneous analysis of multiple astronomical datasets
- **⚖️ Head-to-Head Comparison** - Side-by-side evaluation of different models and datasets
- **📊 Advanced Visualizations** - Interactive charts, probability distributions, and simulated light curves
- **🎯 Role-Based Access Control** - Tailored experiences for Admins, Scientists, and Users
- **🔐 Secure Authentication** - Robust user management with admin approval workflows

### 🎨 User Experience
- **Intuitive Cyberpunk Interface** - Space-themed design with smooth animations and visual feedback
- **Real-time File Validation** - Instant CSV structure verification and data preview
- **Inline Detailed Analysis** - Expandable results without disruptive modal popups
- **Professional Export Capabilities** - Structured data output for further scientific analysis
- **Fully Responsive Design** - Seamless experience across desktop and mobile devices

### 🔧 Technical Excellence
- **RESTful API Architecture** - Well-documented FastAPI endpoints for easy integration
- **Real-time Processing** - Efficient handling of large astronomical datasets
- **Dual-Pipeline Model Management** - Specialized processing for different data sources
- **Scalable Infrastructure** - Architecture designed for high-volume processing demands

---

## 🏗️ System Architecture

### Complete Application Architecture

```mermaid
graph TB
    subgraph "Frontend Layer - React SPA"
        A[🌐 User Browser]
        B[📱 Responsive Components]
        C[🔄 React Router]
        D[🎨 Cyberpunk UI Theme]
        E[📊 Visualization Engine]
        F[🔐 Auth Context]
    end

    subgraph "Backend Layer - FastAPI"
        G[🚀 API Gateway]
        H[📁 File Upload Handler]
        I[🔐 Authentication Service]
        J[🧠 Dual-Pipeline ML Orchestrator]
        K[📈 Visualization Generator]
        L[💾 Data Preprocessor]
    end

    subgraph "Machine Learning - Dual Pipeline"
        subgraph "KOI Pipeline"
            M[KOI XGBoost Model]
            N[KOI GradientBoosting]
            O[KOI StackingEnsemble]
        end
        
        subgraph "K2 Pipeline" 
            P[K2 ExtraTrees Model]
            Q[K2 RandomForest]
            R[K2 XGBoost]
        end
        
        S[⚖️ Pipeline Routing]
        T[📊 Confidence Scoring]
    end

    subgraph "Data Persistence"
        U[📁 CSV File Storage]
        V[💾 Model Artifacts]
        W[🔐 User Sessions]
    end

    A <--> G
    B --> C
    F --> I
    G --> H
    G --> I
    G --> J
    H --> L
    J --> S
    S --> M
    S --> P
    L --> T
    K --> E
    U --> H
    V --> J
    
    style A fill:#1e3a8a,color:#fff
    style G fill:#2563eb,color:#fff
    style M fill:#7c3aed,color:#fff
    style P fill:#10b981,color:#fff
```

### Authentication & Authorization Flow

```mermaid
sequenceDiagram
    participant U as User
    participant UI as React Frontend
    participant Auth as Auth Service
    participant DB as User Database
    participant Router as Navigation

    U->>UI: Access Application
    UI->>Auth: Check Authentication Status
    Auth->>DB: Verify Session Token
    
    alt User Not Authenticated
        UI->>U: Display Login/Signup Forms
        U->>UI: Submit Credentials
        UI->>Auth: Authenticate User
        Auth->>DB: Validate Credentials & Role
        
        alt Valid Scientist Registration
            Auth->>DB: Create Pending Approval
            UI->>U: Show Approval Pending
        else Valid User Registration
            Auth->>DB: Create Active Account
            UI->>Router: Redirect to Predict
        else Admin Authentication
            Auth->>UI: Grant Full System Access
            UI->>Router: Redirect to Admin Dashboard
        end
    else User Authenticated
        Auth->>UI: Return User Role & Permissions
        UI->>Router: Navigate to Role-Specific Dashboard
    end
```

### Multi-File Batch Processing Workflow

```mermaid
graph TB
    A[User Accesses Batch Processing] --> B[Upload Multiple CSV Files]
    B --> C[Frontend Validates Each File]
    C --> D{All Files Valid?}
    D -->|Yes| E[Display File Previews]
    D -->|No| F[Show Validation Errors]
    E --> G[User Selects Data Pipeline & ML Model]
    G --> H[Initiate Batch Analysis]
    H --> I[Parallel API Calls for Each File]
    I --> J[Backend Processes Files Concurrently]
    J --> K[Aggregate Results Across All Files]
    K --> L[Generate Unified Visualizations]
    L --> M[Display Comprehensive Results Dashboard]
    
    style A fill:#88ffff,color:#000
    style E fill:#44ffff,color:#000
    style M fill:#96ceb4,color:#000
```

---

## 📊 Machine Learning Pipeline

### Dual-Pipeline ML System

```mermaid
graph TB
    subgraph "Data Preparation Phase"
        A[📥 Raw Astronomical Data]
        B[🧹 Data Type Detection]
        C{Data Pipeline Selection}
        C -->|KOI Data| D[KOI Feature Engineering]
        C -->|K2 Data| E[K2 Feature Engineering]
        D --> F[KOI Dataset Preparation]
        E --> G[K2 Dataset Preparation]
    end

    subgraph "Model Training Phase"
        subgraph "KOI Pipeline Training"
            H[KOI XGBoost Training]
            I[KOI GradientBoosting Training]
            J[KOI StackingEnsemble Training]
        end
        
        subgraph "K2 Pipeline Training"
            K[K2 ExtraTrees Training]
            L[K2 RandomForest Training]
            M[K2 XGBoost Training]
        end
        
        N[📈 Cross-Validation Evaluation]
    end

    subgraph "Production Inference"
        O[📥 User Data Upload]
        P[🔍 Data Type Detection]
        P -->|KOI| Q[KOI Feature Extraction]
        P -->|K2| R[K2 Feature Extraction]
        Q --> S[🤖 KOI Model Prediction]
        R --> T[🤖 K2 Model Prediction]
        S --> U[📊 Confidence Calculation]
        T --> U
        U --> V[🎨 Visualization Generation]
    end

    F --> H
    F --> I
    F --> J
    G --> K
    G --> L
    G --> M
    H --> N
    I --> N
    J --> N
    K --> N
    L --> N
    M --> N
    O --> P
    
    style C fill:#f59e0b,color:#000
    style P fill:#f59e0b,color:#000
    style V fill:#10b981,color:#fff
```

### Real-time Prediction Workflow

```mermaid
sequenceDiagram
    participant User
    participant Frontend as React Frontend
    participant Backend as FastAPI Backend
    participant ML as ML Models
    participant Viz as Visualization Engine

    User->>Frontend: Upload CSV File & Select Data Pipeline
    Frontend->>Frontend: Validate File Structure & Pipeline Features
    Frontend->>User: Display Data Preview & Validation Status
    
    User->>Frontend: Confirm Analysis Request
    Frontend->>Backend: POST /api/predict with FormData & dataType
    
    Backend->>Backend: Parse CSV & Validate Data Integrity
    Backend->>Backend: Route to Appropriate Pipeline (KOI/K2)
    Backend->>Backend: Apply Pipeline-Specific Feature Engineering
    Backend->>ML: Route to Selected ML Model Pipeline
    
    ML->>ML: Generate Prediction Probabilities
    ML->>ML: Calculate Confidence Scores
    ML->>Viz: Send Structured Prediction Results
    
    Viz->>Viz: Create Pipeline-Specific Visualizations
    Viz->>Viz: Generate Feature Importance Charts
    Viz->>Viz: Convert Plots to Base64 Images
    Viz->>Backend: Return Comprehensive Results Package
    
    Backend->>Frontend: JSON Response with Full Analysis
    Frontend->>Frontend: Render Interactive Results Interface
    Frontend->>Frontend: Display Charts & Statistical Summary
    Frontend->>User: Present Final Analysis Dashboard
```

### Model Performance Characteristics

```mermaid
xychart-beta
    title "Dual-Pipeline Model Performance Comparison"
    x-axis ["KOI XGBoost", "K2 ExtraTrees", "KOI Ensemble", "K2 RandomForest"]
    y-axis "Accuracy Percentage" 85 --> 95
    bar [91.53, 89.72, 90.15, 88.91]
    line [91.53, 89.72, 90.15, 88.91]
```

### Pipeline Feature Importance

```mermaid
pie title KOI Pipeline - Top Predictive Features
    "Orbital Period" : 22
    "Transit Depth" : 18
    "Planet Radius" : 15
    "Equilibrium Temperature" : 12
    "Stellar Insolation" : 10
    "Impact Parameter" : 8
    "Other Features" : 15
```

---

## 🔌 API Documentation

### API Architecture Overview

```mermaid
graph TB
    A[Client Applications] --> B[GET /]
    A --> C[GET /predict]
    A --> D[POST /api/predict]
    A --> E[GET /api/models]
    A --> F[GET /api/health]
    A --> G[GET /api/pipeline-info]
    
    B --> H[HTML: Application Homepage]
    C --> I[HTML: Prediction Interface]
    D --> J[JSON: Analysis Results]
    E --> K[JSON: Model Metadata]
    F --> L[JSON: System Status]
    G --> M[JSON: Pipeline Information]
    
    subgraph "Core API Endpoints"
        D
        E
        F
        G
    end
    
    subgraph "Static Content Delivery"
        B
        C
    end
    
    style D fill:#10b981,color:#fff
    style G fill:#8b5cf6,color:#fff
```

### Request-Response Flow

```mermaid
sequenceDiagram
    participant C as Client
    participant F as FastAPI
    participant P as Preprocessor
    participant M as ML Model
    participant V as Visualizer

    C->>F: POST /api/predict
    Note over C,F: multipart/form-data with<br/>file, model_type & dataType
    
    F->>F: Validate Content-Type & Size
    F->>F: Parse Form Data
    F->>F: Route to Pipeline (KOI/K2)
    F->>P: Extract & Validate CSV Data
    
    P->>P: Check Pipeline-Specific Features
    P->>P: Handle Missing Values
    P->>P: Apply Feature Scaling
    P->>M: Send Processed Features
    
    M->>M: Execute Model Inference
    M->>M: Calculate Probabilities
    M->>M: Generate Confidence Scores
    M->>V: Send Prediction Results
    
    V->>V: Create Pipeline-Specific Visualizations
    V->>V: Generate Base64 Images
    V->>F: Return Structured Response
    
    F->>C: 200 OK with Full Analysis
    Note over F,C: JSON response includes:<br/>- Predictions<br/>- Statistics<br/>- Visualizations<br/>- Pipeline Metadata
```

### Core API Endpoints Specification

#### 🎯 Prediction Endpoint
- **Endpoint**: `POST /api/predict`
- **Purpose**: Process astronomical data through appropriate pipeline and generate exoplanet predictions
- **Content-Type**: `multipart/form-data`
- **Parameters**:
  - `file`: CSV file containing astronomical features
  - `model_type`: ML model selection (pipeline-specific)
  - `dataType`: Pipeline selection (`koi`, `k2`)

**Response Structure:**
```json
{
  "model_used": "KOI_XGBoost",
  "pipeline": "koi",
  "file_info": {
    "filename": "kepler_data.csv",
    "rows_processed": 150,
    "features_used": 16
  },
  "predictions": [
    {
      "row": 1,
      "prediction": "🌍 CONFIRMED",
      "confidence": 0.894,
      "probabilities": {
        "false_positive": 0.043,
        "candidate": 0.063,
        "confirmed": 0.894
      }
    }
  ],
  "statistics": {
    "total_predictions": 150,
    "confirmed_count": 45,
    "confirmed_percentage": 30.0,
    "candidate_count": 60,
    "candidate_percentage": 40.0,
    "false_positive_count": 45,
    "false_positive_percentage": 30.0
  },
  "visualizations": {
    "prediction_plot": "data:image/png;base64,...",
    "feature_importance": "data:image/png;base64,..."
  }
}
```

#### ℹ️ System Information Endpoints
- **Model Information**: `GET /api/models` - Returns loaded model status and pipeline metadata
- **Pipeline Information**: `GET /api/pipeline-info` - Returns available pipelines and capabilities
- **Health Check**: `GET /api/health` - Provides system status and component health
- **Service Discovery**: `GET /` - Main application entry point with documentation links

### Error Handling
The API provides comprehensive error responses for various scenarios:
- **400 Bad Request**: Invalid file format or missing required parameters
- **413 Payload Too Large**: File exceeds maximum allowed size
- **422 Unprocessable Entity**: Data validation failures or pipeline mismatch
- **500 Internal Server Error**: ML model or processing failures

---

## 🛠️ Installation & Setup

### System Requirements
- **Python 3.9+** for backend services and ML operations
- **Node.js 16+** for frontend development and build processes
- **4GB RAM** minimum for efficient model inference
- **2GB disk space** for ML models and dependencies

### Backend Setup Procedure

```mermaid
graph TB
    A[Clone Repository] --> B[Create Virtual Environment]
    B --> C[Install Python Dependencies]
    C --> D[Verify Dual-Pipeline Models]
    D --> E[Start FastAPI Server]
    E --> F[Backend Running on Port 8000]
    
    style A fill:#3b82f6,color:#fff
    style E fill:#10b981,color:#fff
```

**Step-by-step commands:**
```bash
# Clone the repository
git clone https://github.com/koffandaff/spaceex.git
cd spaceex/backend

# Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install required packages
pip install -r requirements.txt

# Verify dual-pipeline model files are present
ls ml_models/koi/
ls ml_models/k2/

# Start the backend server
python app.py
```

### Frontend Setup Procedure

```mermaid
graph TB
    A[Navigate to Frontend] --> B[Install Dependencies]
    B --> C[Start Development Server]
    C --> D[Frontend Running on Port 3000]
    D --> E[Access Application]
    
    style B fill:#3b82f6,color:#fff
    style E fill:#10b981,color:#fff
```

**Step-by-step commands:**
```bash
# Navigate to frontend directory
cd ../frontend

# Install Node.js dependencies
npm install

# Start development server
npm run dev

# Application accessible at http://localhost:3000
```

### Project Structure Overview

```
spaceex/
├── 📁 backend/                         # FastAPI Dual-Pipeline Backend
│   ├── 📁 ml_models/                  # Trained ML Models
│   │   ├── 📁 koi/                    # KOI Pipeline Models
│   │   │   ├── KOI_XGBoost.pkl
│   │   │   ├── KOI_GradientBoosting.pkl
│   │   │   └── KOI_StackingEnsemble.pkl
│   │   └── 📁 k2/                     # K2 Pipeline Models
│   │       ├── k2_ExtraTrees.pkl
│   │       ├── k2_RandomForest.pkl
│   │       └── k2_XGBoost.pkl
│   ├── 📁 static/                     # Frontend Assets
│   ├── 📁 templates/                  # HTML Templates
│   ├── 📁 data/                       # Sample Datasets
│   ├── app.py                         # FastAPI Application
│   ├── train_models.py                # Model Training Script
│   └── requirements.txt               # Python Dependencies
│
└── 📁 frontend/                       # React Application
    ├── public/
    │   └── img.jpg                    # Background Image
    └── src/
        ├── 📁 components/             # React Components
        ├── 📁 context/                # State Management
        ├── 📁 pages/                  # Application Pages
        ├── 📁 services/               # API Integration
        ├── 📁 styles/                 # Styling
        ├── 📁 utils/                  # Utilities
        ├── App.jsx                    # Main Router
        └── main.jsx                   # Application Entry
```

---

## 🎯 Usage Guide

### Complete User Journey

```mermaid
journey
    title SpaceEx User Experience Journey
    section Authentication & Access
      Visit Platform: 5: User
      Complete Authentication: 4: User
      Access Role-Specific Dashboard: 5: User
    section Data Analysis
      Select Data Pipeline (KOI/K2): 5: User
      Upload Astronomical Data: 5: User
      Configure Analysis Parameters: 4: User
      Execute ML Processing: 5: User
    section Results & Insights
      Review Prediction Results: 5: User
      Explore Detailed Analysis: 4: User
      Export Findings: 3: User
```

### Analysis Workflow

```mermaid
graph TB
    A[Access Platform] --> B{User Authentication}
    B -->|Authenticated| C[Role-Based Dashboard]
    B -->|New User| D[Registration Process]
    
    C --> E{Select Analysis Type}
    E --> F[Single File Analysis]
    E --> G[Batch Processing]
    E --> H[Pipeline Comparison]
    
    F --> I[Select Data Pipeline]
    G --> J[Upload Multiple CSVs]
    H --> K[Compare KOI vs K2 Pipelines]
    
    I --> L[Upload Single CSV]
    J --> L
    K --> M[Upload Two Datasets]
    
    L --> N[Select Pipeline-Specific Model]
    M --> O[Select Models for Each Pipeline]
    
    N --> P[Execute Analysis]
    O --> P
    P --> Q[Comprehensive Results Dashboard]
    
    style G fill:#88ffff,color:#000
    style H fill:#44ffff,color:#000
    style Q fill:#96ceb4,color:#000
```

### Input Data Requirements

#### KOI Pipeline Requirements (16 Features):
- `koi_period` - Orbital period in days
- `koi_depth` - Transit depth in parts per million
- `koi_duration` - Transit duration in hours
- `koi_prad` - Planetary radius in Earth radii
- `koi_teq` - Planetary equilibrium temperature
- `koi_insol` - Stellar insolation flux
- `koi_impact` - Impact parameter
- `koi_srad` - Stellar radius in Solar radii
- `koi_slogg` - Stellar surface gravity
- `koi_steff` - Stellar effective temperature
- `koi_kepmag` - Kepler magnitude
- `koi_score` - Disposition score
- `koi_fpflag_co` - Centroid offset flag
- `koi_fpflag_ec` - Ephemeris match flag
- `koi_fpflag_nt` - Not transit-like flag
- `koi_fpflag_ss` - Stellar eclipse flag

#### K2 Pipeline Requirements (16 Features):
- `koi_period` - Orbital period in days
- `koi_impact` - Impact parameter
- `koi_duration` - Transit duration in hours
- `koi_depth` - Transit depth in parts per million
- `koi_prad` - Planetary radius in Earth radii
- `koi_teq` - Planetary equilibrium temperature
- `koi_insol` - Stellar insolation flux
- `koi_srad` - Stellar radius in Solar radii
- `koi_slogg` - Stellar surface gravity
- `koi_steff` - Stellar effective temperature
- `koi_kepmag` - Kepler magnitude
- `koi_score` - Disposition score
- `koi_fpflag_co` - Centroid offset flag
- `koi_fpflag_ec` - Ephemeris match flag
- `koi_fpflag_nt` - Not transit-like flag
- `koi_fpflag_ss` - Stellar eclipse flag

**Example KOI Data Format:**
```csv
koi_period,koi_depth,koi_duration,koi_prad,koi_teq,koi_insol,koi_impact,koi_srad,koi_slogg,koi_steff,koi_kepmag,koi_score,koi_fpflag_co,koi_fpflag_ec,koi_fpflag_nt,koi_fpflag_ss
14.5,738,1.19,1.47,1250,45.2,0.7,0.496,4.65,5800,12.3,0.89,0,0,0,0
```

---

## 👥 Development Team

### Core Contributors

| Role | Contributor | Key Responsibilities |
|------|-------------|---------------------|
| **Full Stack Architect** | Dhruvil | System architecture, React-FastAPI integration, Authentication system |
| **UI/UX Specialist** | Vraj | Cyberpunk theme design, User interface implementation, Visual design system |
| **Machine Learning Engineer** | Krisha | Dual-pipeline model development, Feature engineering, Model training pipeline |
| **Backend & DevOps** | Akshat | FastAPI development, Deployment infrastructure, Performance optimization |
| **Data Science Lead** | Parth | Data processing, Analytical methodologies, Scientific validation |

### Development Methodology

```mermaid
graph TB
    A[Feature Specification] --> B[Architecture Design]
    B --> C[Implementation Phase]
    C --> D[Quality Assurance]
    D --> E[Code Review]
    E --> F[Integration Testing]
    F --> G[Staging Deployment]
    G --> H[User Acceptance Testing]
    H --> I[Production Release]
    
    subgraph "Quality Gates"
        C --> J[Unit Test Coverage]
        D --> K[Integration Tests]
        F --> L[Performance Validation]
        F --> M[Security Assessment]
    end
    
    subgraph "Team Collaboration"
        B --> N[Technical Design Review]
        E --> O[Peer Code Review]
        G --> P[Stakeholder Demo]
    end
    
    style C fill:#0ea5e9,color:#fff
    style I fill:#10b981,color:#fff
```

---

## 🤝 Contributing

We enthusiastically welcome contributions from the astronomical, machine learning, and open source communities! Here's how you can participate:

### Development Environment Setup

```mermaid
graph TB
    A[Fork Repository] --> B[Clone Your Fork]
    B --> C[Create Feature Branch]
    C --> D[Set Up Development Environment]
    D --> E[Implement Changes]
    E --> F[Run Test Suite]
    F --> G[Submit Pull Request]
    G --> H[Code Review Process]
    H --> I[Merge to Main]
    
    style A fill:#3b82f6,color:#fff
    style F fill:#f59e0b,color:#000
    style I fill:#10b981,color:#fff
```

### Contribution Areas

- **🔬 Machine Learning Innovations**
  - New pipeline development for TESS and other missions
  - Advanced feature engineering techniques
  - Model interpretability and explainability

- **📊 Visualization & Analytics**
  - Interactive 3D visualizations and celestial maps
  - Advanced statistical analysis tools
  - Real-time data streaming displays

- **🌐 Platform Extensions**
  - Additional API endpoints for specialized analyses
  - Mobile application development
  - Internationalization and accessibility

- **🔧 Performance & Scalability**
  - Database integration for large datasets
  - Caching strategies and optimization
  - Parallel processing enhancements

### Contribution Guidelines
1. Follow existing code style and architectural patterns
2. Include comprehensive tests for new functionality
3. Update documentation for API and interface changes
4. Ensure backward compatibility when possible
5. Participate actively in code review discussions
6. Adhere to the project's code of conduct

---

## 🔮 Future Scope

### Platform Evolution Roadmap

```mermaid
graph TB
    A[Platform Evolution] --> B[Additional Data Pipelines]
    A --> C[Advanced Analytics Suite]
    A --> D[Real-time Processing Engine]
    A --> E[Collaborative Research Features]
    
    B --> F[TESS Mission Pipeline]
    B --> G[Ground-based Surveys]
    B --> H[JWST Integration]
    B --> I[Custom Pipeline Creation]
    
    C --> J[Time-Series Analysis]
    C --> K[Statistical Significance Testing]
    C --> L[Uncertainty Quantification]
    
    D --> M[Streaming Data Integration]
    D --> N[Live Telescope Data Feeds]
    D --> O[Real-time Discovery Alerts]
    
    E --> P[Research Team Workspaces]
    E --> Q[Collaborative Annotation System]
    E --> R[Publication Preparation Tools]
    
    style B fill:#f59e0b,color:#000
    style F fill:#8b5cf6,color:#fff
```

### Scientist Model Retraining System
- **Dedicated Research Dashboard** - Specialized interface for data scientists and astronomers
- **Automated Training Pipeline** - Streamlined process for model retraining with new datasets
- **Performance Monitoring** - Continuous evaluation of model accuracy and drift detection
- **Version Control** - Comprehensive model versioning and experiment tracking
- **A/B Testing Framework** - Comparative analysis of different model versions

### Advanced Capabilities
- **Citizen Science Integration** - Public participation in exoplanet discovery and validation
- **Educational Modules** - Teaching resources and interactive learning experiences
- **Open Data Initiative** - Sharing discoveries and datasets with global research community
- **API Marketplace** - Third-party integrations and specialized analysis tools

### Long-term Vision
- **Global Research Network** - Connecting astronomers and institutions worldwide
- **AI-Driven Discovery** - Autonomous observation planning and anomaly detection
- **Multi-wavelength Analysis** - Integrating data across different observational techniques
- **Exoplanet Characterization** - Moving beyond detection to detailed planetary analysis

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for complete details.

### Acknowledgments
- **NASA Exoplanet Archive** - For foundational datasets and validation resources
- **Kepler & K2 Missions** - For the revolutionary astronomical data that enables this research
- **FastAPI Community** - For exceptional documentation, support, and continuous improvement
- **Scikit-learn Ecosystem** - For robust, well-documented machine learning tools
- **React Community** - For comprehensive component libraries and development tools

### Citation
If you use SpaceEx in your research or publications, please cite:
```bibtex
@software{spaceex2024,
  title = {SpaceEx: Advanced Exoplanet Detection Platform},
  author = {SpaceEx Development Team},
  year = {2024},
  url = {https://github.com/koffandaff/spaceex},
  note = {Dual-Pipeline Machine Learning Platform for Astronomical Discovery}
}
```

---

<div align="center">

## 🌟 Discover the cosmos one prediction at a time with SpaceEx 🌟

**Ready to explore distant worlds and advance astronomical discovery?**

[🚀 Get Started](#️-installation--setup) • 
[📚 Explore Documentation](#) • 
[👥 Join Our Community](#)

*SpaceEx: Where cutting-edge artificial intelligence meets the timeless wonder of cosmic exploration* 🚀🌌

</div>

---

<div align="center">

*Built with ❤️ for the advancement of astronomy and open science*

[![GitHub stars](https://img.shields.io/github/stars/koffandaff/spaceex?style=social)](https://github.com/koffandaff/spaceex/stargazers)
[![GitHub forks](https://img.shields.io/github/forks/koffandaff/spaceex?style=social)](https://github.com/koffandaff/spaceex/network/members)
[![GitHub issues](https://img.shields.io/github/issues/koffandaff/spaceex)](https://github.com/koffandaff/spaceex/issues)

</div>
```

## Key Updates Made:

1. **Dual-Pipeline Architecture**: Updated all sections to reflect the KOI/K2 dual-pipeline system
2. **Updated Tech Stack**: Added specific ML models and their accuracies for both pipelines
3. **Enhanced Features**: Updated feature lists to include pipeline-specific capabilities
4. **Revised Architecture Diagrams**: Updated system architecture to show dual-pipeline flow
5. **Updated API Documentation**: Added `dataType` parameter and pipeline-specific endpoints
6. **New Installation Instructions**: Updated to reflect dual-pipeline model structure
7. **Updated Input Requirements**: Added specific feature requirements for KOI and K2 pipelines
8. **Enhanced Usage Guide**: Updated workflows to include pipeline selection
9. **Updated Team Responsibilities**: Reflected the dual-pipeline development work
10. **Future Scope**: Added TESS and other mission pipeline expansions

The README now accurately reflects the current state of the SpaceEx platform as documented in the changelog, including the dual-pipeline architecture, enhanced authentication system, batch processing capabilities, and all other features developed through Sprint 6.# readme
