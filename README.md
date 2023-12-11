# QueryCortex.com MVP Architecture

## Overview
This document outlines the MVP architecture for QueryCortex.com, a web-based AI platform for conducting and analyzing candidate interviews using WebRTC and OpenAI.

## Architecture Components for MVP

### 1. Resume Parsing
- **Profilytics.com API**: 
  - Purpose: Extract candidate information and skills from resumes.

### 2. Interview Question and Answer Database
- **Local Database (MongoDB)**: 
  - Purpose: Store predefined interview questions and answers.

### 3. Candidate Interaction Interface
- **WebRTC for Audio Communication**: 
  - Purpose: Conduct interviews via web-based real-time audio.
  - Functionality: Stream audio for voice-to-text processing.

### 4. AI-Based Response and Performance Analysis
- **External AI API (OpenAI)**: 
  - Purpose: Analyze candidate's spoken responses for correctness using voice-to-text.
  - Functionality: Assess responses against the job description and resume data.

### 5. AI-Driven Test Administration
- **Node.js Backend (Maintain FastAPI for Future Expansion)**: 
  - Purpose: Utilize Node.js for handling current AI logic and data processing.
  - Note: Retain FastAPI framework for potential future use with custom AI models.

### 6. Data Storage and Management
- **Local MongoDB Instance**: 
  - Purpose: Store interview data, including transcripts and analysis results.

### 7. Application Backend
- **Node.js (Primary Backend)**: 
  - Purpose: Manage application logic, API calls to OpenAI, and orchestration with WebRTC.

### 8. Frontend Application
- **Web Application (React)**: 
  - Purpose: Interactive interface for conducting and managing interviews.

### 9. Containerization and Deployment
- **Docker and Docker Compose**: 
  - Purpose: Efficient deployment and scaling of the application components.

### 10. Monitoring and Maintenance
- **Self-Hosted Monitoring Tools (e.g., Prometheus, Grafana)**: 
  - Purpose: Ensure optimal performance and health of the application.

## Conclusion for MVP
The MVP of QueryCortex.com focuses on establishing core functionalities with WebRTC for audio-based interviews and leveraging OpenAI for intelligent response analysis, setting the foundation for a scalable, AI-driven interview platform.
