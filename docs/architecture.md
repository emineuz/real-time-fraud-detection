# System Architecture

## Overview

The project follows a real-time data pipeline architecture. Transaction data is streamed through Kafka, processed by a consumer service, evaluated by a fraud detection model, and stored in PostgreSQL. The processed results are then served through an API and visualized in a dashboard.

## Architecture Flow

```text
Transaction Dataset
        ↓
Kafka Producer
        ↓
Kafka Topic
        ↓
Kafka Consumer
        ↓
ML Fraud Detection Model
        ↓
PostgreSQL Database
        ↓
FastAPI Backend
        ↓
Streamlit Dashboard
```

## Components

### Transaction Dataset

A financial transaction dataset will be used as the source data. The data will be streamed row by row to simulate real-time transactions.

### Kafka Producer

The producer will read transaction records and send them to a Kafka topic.

### Kafka Consumer

The consumer will listen to the Kafka topic, process incoming transactions, apply the fraud detection model, and store the results.

### Machine Learning Model

A supervised machine learning model will classify transactions as fraudulent or legitimate.

### PostgreSQL Database

PostgreSQL will store raw transactions, prediction results, and risk scores.

### FastAPI Backend

FastAPI will provide endpoints for accessing transaction and prediction data.

### Streamlit Dashboard

The dashboard will visualize transaction volume, fraud counts, recent predictions, and high-risk transactions.

## Planned Improvements

- Model experiment tracking
- Data quality checks
- Workflow orchestration
- Monitoring and logging
- Explainable risk analysis