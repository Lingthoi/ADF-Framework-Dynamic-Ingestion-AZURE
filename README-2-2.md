![Azure](https://img.shields.io/badge/Azure-Cloud-blue)
![Azure Data Factory](https://img.shields.io/badge/Azure%20Data%20Factory-ADF-blue)
![Data Engineering](https://img.shields.io/badge/Data%20Engineering-ETL%20%7C%20ELT-success)
![CI/CD](https://img.shields.io/badge/CI%2FCD-GitHub-black)
![REST API](https://img.shields.io/badge/REST%20API-Ingestion-orange)
![Status](https://img.shields.io/badge/Project-Production--Ready-brightgreen)

# 🚀 Azure Data Factory Pro – Enterprise Data Ingestion Framework

A modular Azure Data Factory ingestion framework, where each module addresses a real-world data engineering scenario commonly found in enterprise data platforms.

---

## 📌 Project Overview

This project showcases a production-grade Azure Data Engineering solution built using Azure Data Factory (ADF). Rather than focusing on a single pipeline, it's designed as a collection of reusable ingestion patterns — reflecting how real enterprise data platforms are built and maintained.

Each module solves a specific data engineering problem: incremental database loads, API ingestion, schema variability, monitoring, and CI/CD.

---

### 🎯 Why a Modular Design?

In real-world organizations:

- Data comes from multiple source types (databases, APIs, files)
- Each source presents different ingestion challenges
- Pipelines must be scalable, reusable, and easy to maintain
- Monitoring and deployment are platform-level responsibilities

👉 This project is intentionally modular to demonstrate:

- Pattern-based engineering
- Platform thinking over one-off pipelines
- How data engineers design enterprise-ready ingestion frameworks

---

## 📦 Core Modules & Real-World Scenarios

### 🔹 Incremental SQL Data Load (Delta Strategy)

**Scenario:** Transactional databases where only new or updated records should be processed.

- Timestamp-based watermark (`last_updated`)
- Handles late-arriving / backdated data
- Avoids full-table reloads
- Cost-efficient and scalable design

<img width="1025" height="369" alt="Incremental load pipeline" src="https://github.com/user-attachments/assets/c5140483-68d0-44db-8c74-6cb5de35edd8" />

<img width="587" height="260" alt="Watermark configuration" src="https://github.com/user-attachments/assets/108f65c7-6c67-48a7-8cfc-ab08ff853419" />

### 🔹 REST API Ingestion with Dynamic Pagination

**Scenario:** Third-party APIs that return data in pages.

- Range-based pagination
- Automatically retrieves all available records
- Scales without manual looping
- API rate-limit aware design

<img width="944" height="746" alt="API pagination pipeline" src="https://github.com/user-attachments/assets/8314bff5-5c2e-4575-935a-2fb84a81bb0d" />

### 🔹 Metadata-Driven File Ingestion

**Scenario:** Regular file drops from multiple teams or vendors.

- Single dynamic dataset
- Auto-discovery of files
- ForEach + Switch-based routing
- Eliminates pipeline and dataset sprawl

<img width="1103" height="342" alt="File ingestion pipeline" src="https://github.com/user-attachments/assets/734ba214-7c9e-4d50-b546-4d369506a9c9" />

### 🔹 Dynamic Schema Mapping

**Scenario:** Multiple business entities with different schemas but identical ingestion flow.

- Schema mappings passed as JSON parameters
- Runtime schema selection
- One pipeline supports multiple structures
- Prevents schema-related pipeline failures

<img width="758" height="598" alt="Schema mapping pipeline" src="https://github.com/user-attachments/assets/081a1806-50d2-432d-8d3b-88e072a987b0" />

### 🔹 Monitoring & Failure Alerts

**Scenario:** Production pipelines requiring immediate operational visibility.

- Azure Logic App integration
- Automated email alerts
- Captures pipeline context (run ID, table, pipeline name)
- Covers silent and skipped failures

<img width="512" height="234" alt="Monitoring and alerting flow" src="https://github.com/user-attachments/assets/b333b401-d2ea-4249-8c89-423d915f5144" />

### 🔹 CI/CD with GitHub Integration

**Scenario:** Multiple engineers working on shared data pipelines.

- Git-based version control
- Feature branching & pull requests
- ARM & YAML artifact generation
- Safe deployments and rollback capability

---

## 🧠 Skills Demonstrated

| Module | Problem Solved | Key Tech |
|---|---|---|
| Incremental Loads | Optimized delta ingestion | ADF, SQL |
| API Pagination | Scalable ingestion of third-party APIs | ADF, REST |
| Metadata-Driven Files | Multi-file ingestion | ADF, Parameters |
| Schema Mapping | Dynamic schema support | ADF, JSON Mappings |
| Monitoring | Alerts & operational readiness | ADF, Logic Apps |
| CI/CD | GitOps workflow | GitHub, ADF |

---

## 🏁 Conclusion

This project establishes a high-maturity, metadata-driven data engineering framework on Azure — transitioning from static ETL tasks to enterprise-grade orchestration. By decoupling logic from data and implementing a self-cleaning, event-driven architecture, the platform achieves:

- **Scalability & Reusability** — Parameterization and dynamic mapping handle multi-entity ingestion (customers, drivers, trips) through a single code path, minimizing technical debt.
- **Cost & Resource Optimization** — Watermark-based incremental loading (delta loads) and logical gating ensure Azure consumption is limited to only changed datasets.
- **Operational Resilience** — Automated data validation, REST API pagination logic, and Logic App webhooks enable real-time monitoring and proactive error alerting.
- **DataOps & CI/CD Excellence** — A robust software development lifecycle (SDLC) built on GitHub version control, feature branching, and automated ARM/YAML template generation for seamless multi-environment deployment.

This framework reflects a modern, production-ready approach to building sustainable, cost-effective, and metadata-driven data platforms in the cloud.
