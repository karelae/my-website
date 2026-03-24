# Back-end QA Approach

> **Project:** imec
> **Status:** Work in progress (WIP)

---

## API Testing Overview

| Test Type | Focus Areas | Key Examples |
|---|---|---|
| **Unit Tests** | Component logic, file patterns, data processing | • Regex tests for TEM file naming<br>• Configuration validation<br>• Business logic functions |
| **Integration Tests** | API security, endpoints, Azure integration | • LBAC (Lot-Based Access Control)<br>• Filter APIs with real auth<br>• Blob storage workflows |
| **Deployment Tests** | Infrastructure validation | • Service health checks |

### Key Testing Patterns

| | Pattern | Description |
|---|---|---|
| 🔒 | **Security-First** | Extensive LBAC ensuring users only see authorized lots |
| 🎯 | **Real-World Complexity** | Complex TEM microscopy file naming patterns |
| ☁️ | **Azure-Native** | Blob Storage, Cosmos DB, Service Bus integration |
| 🧪 | **Mock-Heavy** | Proper external dependency isolation |

### Technology Stack

- pytest, FastAPI TestClient, polars DataFrames
- Azure: Identity, Blob Storage, Cosmos DB, Service Bus
- Sophisticated mocking for external dependencies

---

## Why e2e API Testing is Needed

- Technical correctness
- API contracts
- Business workflows
- Real production data
- Deployed Application Testing
- Regression Detection for User Impact
- Can be 100% automated. No visual checks required.

> ⚠️ **WIP** — e2e test suite is currently being built out.

---

## Security

### LBAC (Lot-Based Access Control)

- Verify users only access authorized lots
- Test cross-lot data isolation
- Validate role-based endpoint restrictions
- Test unauthorized access returns 403

### Authentication & Authorization

- Azure Identity integration tests
- Token validation and expiry handling
- Filter APIs with real auth flows
- Service-to-service auth verification

### Data Protection

- Sensitive data not exposed in responses
- Cosmos DB document-level access control
- Blob Storage SAS token scoping
- PII handling compliance checks

### Infrastructure Security

- Service Bus connection security
- Azure Key Vault secret rotation
- Network access policy validation
- Health check endpoint exposure audit
