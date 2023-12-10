# QueryCortex.com Architecture

## Overview
This document details the architecture for QueryCortex.com, an AI-based platform designed for conducting and analyzing candidate interviews using voice-to-text and text-to-voice technologies, based on resumes and job descriptions.

## Architecture Components

### Root
Central node of the application architecture.

#### Resume Parsing
- **Profilytics.com API**
  - Extract candidate information and skills from resumes

#### Interview Question and Answer Database
- **Local Database (MongoDB)**
  - Store pre-defined interview questions and answers

#### Candidate Interaction Interface
- **Voice-to-Text and Text-to-Voice Technologies**
  - Conduct interviews over the phone
  - Convert voice to text for analysis and text to voice for interaction

#### AI-Based Response and Performance Analysis
- **External AI API (e.g., OpenAI)**
  - Analyze candidate responses for correctness
  - Determine appropriate tests based on job description and resume

#### AI-Driven Test Administration
- **Custom AI Logic (Node.js / FastAPI)**
  - Decide which tests to administer based on AI analysis

#### Data Storage and Management
- **Local MongoDB Instance**
  - Store candidate data, interview transcripts, test results

#### User Management and Authentication
- **OAuth and Social Logins (e.g., Google, LinkedIn)**
  - Manage user authentication

#### Application Backend
- **Node.js (Primary Backend)**
  - Handle application logic and data orchestration
- **FastAPI (Python)**
  - Handle CPU-intensive analysis and AI interactions

#### Frontend Application
- **Web Application (React)**
  - User interface for candidates and recruiters

#### Containerization and Deployment
- **Docker and Docker Compose**
  - Containerize all application components
  - Deploy as a single stack

#### Monitoring and Maintenance
- **Self-Hosted Monitoring Tools (e.g., Prometheus, Grafana)**
  - Monitor application performance
  - Alerting and system health reporting
