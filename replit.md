# Replit.md

## Overview

This is a Streamlit-based web application for YouTube live streaming management. The application integrates with Google OAuth for YouTube API authentication and uses FFmpeg for video streaming operations. It appears to be a live news streaming tool that allows users to manage YouTube live streams through a web interface.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend
- **Framework**: Streamlit - Python-based web framework for data applications
- **UI Components**: Uses Streamlit's native components plus custom HTML/JavaScript via `streamlit.components.v1`
- **Rationale**: Streamlit provides rapid prototyping for Python-centric applications with minimal frontend code

### Backend
- **Language**: Python 3.11
- **Runtime**: Single-file application (`app.py`) that handles all logic
- **Pattern**: Monolithic architecture - all functionality in one file for simplicity

### Authentication
- **Method**: Google OAuth 2.0 for YouTube API access
- **Libraries**: google-auth, google-auth-oauthlib, google-api-python-client
- **Configuration**: Hardcoded OAuth credentials for the "anjelikakozme" project
- **Redirect URI**: Configured for streamlit.app deployment

### Data Storage
- **Database**: SQLite for persistent logging (`streaming_logs.db`)
- **Purpose**: Stores streaming activity logs locally
- **Rationale**: Lightweight, file-based storage suitable for single-instance deployments

### Video Processing
- **Tool**: FFmpeg (system-level dependency via packages.txt)
- **Python Bindings**: ffmpeg-python, opencv-python-headless
- **Purpose**: Handles video stream encoding and transmission to YouTube

## External Dependencies

### Google APIs
- **YouTube Data API v3**: For managing live streams and broadcasts
- **OAuth 2.0**: User authentication flow
- **Endpoint**: Uses googleapis.com services

### System Packages
- **FFmpeg**: Required for video encoding/streaming (installed via packages.txt)

### Python Libraries (Key Dependencies)
- `streamlit`: Web application framework
- `google-api-python-client`: YouTube API client
- `google-auth-oauthlib`: OAuth authentication flow
- `opencv-python-headless`: Video frame processing
- `ffmpeg-python`: FFmpeg Python bindings
- `pytube`: YouTube video utilities
- `psutil`: System monitoring
- `requests`: HTTP client for API calls

### Deployment Configuration
- **Container**: Uses Microsoft's Python 3.11 devcontainer image
- **Port**: 8501 (Streamlit default)
- **CORS/XSRF**: Disabled for development convenience