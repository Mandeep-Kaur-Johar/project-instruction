# Security Rules for Agentic SDLC Platform

## Purpose

This document defines mandatory security rules that all AI agents, MCP tools, workflows, and users must follow.

---

## Core Security Principles

1. Follow least-privilege access.
2. Deny by default when authorization cannot be validated.
3. Never expose secrets, credentials, tokens, or sensitive information.
4. Validate all inputs before processing.
5. Log security-relevant actions.
6. Require human approval for high-risk operations.
7. Follow organizational security and compliance policies.

---

## Authentication Rules

### AUTH-001
All users must be authenticated before accessing protected resources.

### AUTH-002
Enterprise identity providers such as Microsoft Entra ID must be used where available.

### AUTH-003
Authentication tokens must be validated for:
- Issuer
- Audience
- Expiration
- Signature

### AUTH-004
Expired or invalid tokens must be rejected.

### AUTH-005
Anonymous access is prohibited unless explicitly approved.

---

## Authorization Rules

### AUTHZ-001
Authentication does not imply authorization.

### AUTHZ-002
Every protected operation must verify user permissions.

### AUTHZ-003
Role-based access control (RBAC) must be enforced.

### AUTHZ-004
Administrative functions must be restricted to authorized administrators.

### AUTHZ-005
Agents must not bypass authorization checks.

---

## Secrets Management Rules

### SEC-001
Secrets must never be stored in source code.

### SEC-002
Secrets must not be stored in markdown instruction files.

### SEC-003
Secrets must not be logged.

### SEC-004
Use approved secret-management platforms.

### SEC-005
Rotate credentials according to organizational policy.

---

## Data Protection Rules

### DATA-001
Only collect data required for the business process.

### DATA-002
Sensitive information must be masked where appropriate.

### DATA-003
Data must be encrypted in transit.

### DATA-004
Sensitive data must be protected at rest.

### DATA-005
Agents must not expose confidential information to unauthorized users.

---

## Agent Security Rules

### AGENT-001
Agents must execute only within their assigned responsibilities.

### AGENT-002
Agents must not invent credentials, URLs, IDs, secrets, or configuration values.

### AGENT-003
Agents must request clarification when required information is unavailable.

### AGENT-004
Agents must not execute destructive actions without authorization.

### AGENT-005
All agent actions must be traceable.

---

## MCP Security Rules

### MCP-001
MCP servers must require authentication.

### MCP-002
MCP tools must validate inputs.

### MCP-003
MCP endpoints must use HTTPS.

### MCP-004
Tool access must be restricted by role.

### MCP-005
MCP execution logs must be retained according to policy.

---

## AI Safety Rules

### AI-001
Do not generate fabricated business data.

### AI-002
Do not fabricate approvals.

### AI-003
Do not fabricate test evidence.

### AI-004
Do not bypass validation workflows.

### AI-005
Flag missing information rather than guessing.

---

## Logging and Monitoring Rules

### LOG-001
All critical actions must be logged.

### LOG-002
Security failures must be logged.

### LOG-003
Logs must not contain secrets.

### LOG-004
Every request should contain a correlation ID.

### LOG-005
Audit records must be retained according to compliance requirements.

---

## Human Approval Gates

Human approval is required for:
- Production deployments
- Deletion operations
- Security configuration changes
- Access-control modifications
- Infrastructure destruction
- High-risk financial or business actions

---

## Security Validation Checklist

- Authentication implemented
- Authorization validated
- Secrets protected
- Input validation completed
- Logging enabled
- Monitoring enabled
- Encryption enabled
- Audit trail available
- Human approval checkpoints defined
- Security review completed

---

## Agent Enforcement Statement

If a request violates any rule in this document, the agent must:
1. Stop execution.
2. Explain the violated rule.
3. Request corrective action.
4. Record the event when logging is available.

