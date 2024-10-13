# Slack-like System Architecture

![Architecture Diagram](artifacts/architecture.svg)

## Overview

This project is a scalable, real-time messaging system similar to Slack, designed using a microservices architecture.

## Architecture Components

- **Client Applications**: Web, desktop, and mobile interfaces.
- **API Gateway**: Routes requests to services.
- **Microservices**:
  - Authentication Service
  - Messaging Service
  - Notification Service
  - File Storage Service
  - Search Service
- **Databases and Storage**:
  - User Database
  - Message Database
  - File Storage
  - Search Index
- **Real-Time Communication**: WebSocket servers.

## Generating the Architecture Diagram

The architecture diagram is created using the [D2 diagramming language](https://d2lang.com/).

### Steps to Generate Locally:

1. **Install D2**:

   ```bash
   curl -fsSL https://d2lang.com/install.sh | sh -s --
   sudo mv d2 /usr/local/bin/
   ```

2. **Generate the Diagram**:

  ```bash
  mkdir -p artifacts
  d2 --theme 200 architecture.d2 artifacts/architecture.svg
  ```


This command reads `architecture.d2` and generates an SVG diagram in the `artifacts/` directory.

## Continuous Integration

The CI pipeline is configured to automatically generate the architecture diagram on each commit to the main branch. The pipeline uses GitHub Actions defined in `.github/workflows/diagram.yml`.

## CI Pipeline Overview
- **Install D2**: The pipeline installs D2 in the CI environment.
- **Generate Diagram**: Converts `architecture.d2` into `artifacts/architecture`.svg.
- **Upload Artifact**: The generated SVG file is uploaded as a build artifact for easy access.