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

# QueryCortex.com Architecture Overview

## Overview
This document outlines the architecture integrating WebRTC with FastAPI, OpenAI, and other components, focusing on efficient data flow and resource management.

## Architecture Components

### 1. WebRTC for Real-Time Audio Communication
- **Function**: 
  - Handles real-time audio communication with candidates.
- **Integration**: 
  - WebRTC streams are managed in the browser and sent to the Node.js backend.

### 2. Voice Activity Detection (VAD)
- **Placement**: 
  - Ideally integrated within the Node.js layer for immediate processing of audio streams.
- **Function**: 
  - Detects when the user starts and stops speaking during the WebRTC session.

### 3. Voice-to-Text Conversion
- **Service Choice**: 
  - Can use external APIs or custom solutions.
- **Handling**: 
  - Managed by FastAPI for CPU-intensive tasks. Audio stream from WebRTC is sent to FastAPI for conversion.

### 4. Interaction with OpenAI for AI-Based Analysis
- **FastAPI Endpoint**: 
  - Receives transcribed text from the voice-to-text service.
- **Function**: 
  - Sends text to OpenAI API for analysis and receives AI-generated responses.

### 5. Text-to-Voice Conversion
- **Service**: 
  - Converts AI-generated text responses back into speech.
- **Handling**: 
  - Managed by FastAPI for efficiency.

### 6. Node.js Backend
- **Role**: 
  - Central orchestrator, managing WebRTC sessions, VAD data, and coordination between frontend, FastAPI, and other services.
- **Database Interaction**: 
  - Interfaces with local MongoDB instance for data storage.

### 7. MinIO File Storage
- **Integration**: 
  - Node.js and FastAPI interact with MinIO for storing and retrieving audio files, transcripts, and other data.

### 8. Data Flow
- **From WebRTC to AI Analysis**: 
  - Audio data flows from WebRTC to Node.js, then to FastAPI for voice-to-text conversion, and to OpenAI.
- **Database and File Storage**: 
  - All components interact with MongoDB and MinIO, facilitated by Node.js backend.

### 9. Containerization and Deployment
- **Docker Containers**: 
  - Each component (Node.js, FastAPI, MongoDB, MinIO) is containerized.
- **Docker Compose**: 
  - Manages deployment and orchestration.

## System Considerations
- **Scalability**: 
  - FastAPI's asynchronous capabilities are key for CPU-intensive tasks.
- **Resource Management**: 
  - Important for transcription and text-to-speech services.
- **Latency**: 
  - Minimize latency in audio processing and AI response generation.

## Conclusion
This architecture leverages both Node.js and FastAPI, ensuring efficient real-time audio processing, AI interactions, and data management for a seamless AI-driven interview platform.
