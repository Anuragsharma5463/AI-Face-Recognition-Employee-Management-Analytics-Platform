# Table of Contents
Project Overview
Key Features
Application Screenshots & Visual Tour
System Architecture
AI / Computer Vision Pipeline
Milvus Vector Database Topology
Asynchronous Queue & Worker Architecture
Product Walkthrough & User Guide
Dashboard Analytics & Telemetry
Technology Stack
Repository Structure
Prerequisites
Environment Configuration
Quick Start with Docker
Local Development Setup
API Documentation & Endpoints
Database Schema & ER Relationships
Troubleshooting & Diagnostics
Security & Biometric Privacy
Performance & Scalability
Production Deployment Recommendations
Project Roadmap
Author

# 🌟 Project Overview
Traditional employee attendance and access management systems frequently suffer from buddy punching, physical credential loss, slow manual logbooks, and fragmented operational telemetry.

The Face Recognition Employee Management & Analytics Platform delivers an automated, enterprise-ready biometric platform built with FastAPI, React 19, Milvus Vector DB, InsightFace (buffalo_l), and RabbitMQ.

What Problems Does This Platform Solve?
Asynchronous Video Enrollment: Ingests onboarding videos via message queues, parses high-quality facial frames using Laplacian variance and pose metrics, extracts 512-dimensional ArcFace embeddings, and indexes them into Milvus without blocking API threads.
Sub-10ms Approximate Nearest Neighbor (ANN) Recognition: Executes real-time cosine similarity search across indexed employee galleries with high precision verification and spoof/outlier rejection.
Enterprise Multi-Attribute Governance: Organizes employees by Departments, Designations, and Operational Shifts with dynamic grace-period configurations.
Live 6-Tier Intelligence Dashboard: Tracks biometric health compliance, completion targets, spline-based enrollment trajectories, multi-dimensional vertical/pie distributions, workforce turnaround, and live audit feeds



#Key Features
👥 Enterprise Workforce Governance
Full Employee Directory CRUD: Profile management with unique employee codes, corporate email, phone, and joining date telemetry.
Organizational Taxonomies: Dynamic Department allocation and Designation classifications.
Operational Shift Management: Multi-shift scheduling with custom start times, end times, and configurable grace period minutes.
Multi-Attribute Global Filters: Filter system metrics across department, shift, designation, and employment status simultaneously.
🧑‍💻 Asynchronous Biometric Face Enrollment
Video & Camera Ingestion: Upload MP4/AVI enrollment recordings or capture live camera streams.
Automated Quality Filtering: Laplacian variance blur filtering, illumination thresholds, and bounding box validation.
Centroid Vector Generation: Generates averaged 512-D L2-normalized feature vectors across top candidate frames.
Resilient Background Processing: RabbitMQ task queue (face_enrollment_queue) with persistent retry mechanisms and detailed failure telemetry.


# Real-Time Face Recognition Engine
InsightFace (buffalo_l): RetinaFace detection and ArcFace deep metric learning for high-accuracy feature extraction.
Milvus HNSW Vector Search: ANN vector search using Cosine distance metric with sub-10ms query latency.
Live Verification Console: Upload test photos or connect live webcams to receive instant match confidence scores, employee identity metadata, and latency diagnostics.
Threshold Security Guardrails: Configurable verification boundary (default 0.45 / 0.60) with automated access rejection for unknown faces.


# 6-Tier Command & Telemetry Dashboard
Summary KPI Strip: Real-time cards for Total Workforce, Active Profiles, Face Enrolled, and Pending Action with export capabilities.
Biometric Analytics Grid:
Face Enrollment Overview: SVG linear-gradient donut chart with ambient glow, central rate readout, and 2x2 metric indicators.
Face Enrollment Trend: Fluid cubic Bezier curves, dual-tone gradient fills, interactive KPI badges, and floating crosshair tooltips.
Enrollment Completion Target: Semi-circular top-arch SVG goal gauge with 95% enterprise milestone marker and aging triage queue (>7D, >30D).
Department Enrollment Health: Interactive health filter tabs (All, High ≥85%, Moderate 70–84%, Attention <70%) with dual-tone compliance bars.
Workforce Matrix: Interactive Vertical Column Bar Chart and Pie / Donut (%) Share Mode across Departments, Shifts, and Designations with automated insight highlights.
Growth & Turnaround: Dual-mode trajectory curves and bi-directional New Joiners vs Exits turnaround analysis.
AI Vector Cluster Telemetry: Real-time Milvus cluster health, 512-D density telemetry, and Cosine similarity spectrum classification.
Recent Biometric Audit Stream: Live event feed with responsive Grid View and List View modes, filter tabs (All, Completed, Issues), and direct drilldown links.



