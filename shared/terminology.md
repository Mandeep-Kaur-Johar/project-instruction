# Agentic SDLC Terminology Reference

## Business Analysis Terms

### Epic
A large business initiative that is broken down into multiple features and user stories.

### Feature
A business capability that delivers value to users and is decomposed into user stories.

### User Story
A requirement written from an end-user perspective.

Format:
As a <role>,
I want <goal>,
So that <business value>.

### Acceptance Criteria
Testable conditions that must be satisfied for a user story to be considered complete.

### Persona
A representation of an end user, stakeholder, or system actor.

### Business Rule
A policy, constraint, or decision governing business behavior.

### Assumption
A statement considered true until validated.

### Dependency
An external item required before implementation can proceed.

### Risk
A potential event that may negatively impact delivery, quality, security, or schedule.

---

## Solution Architecture Terms

### Architecture Decision
A documented technical decision with rationale and consequences.

### Solution Architecture
The high-level design of the complete solution.

### Component
A logical or physical building block within a solution.

### Integration
Interaction between systems, applications, services, or APIs.

### API
Application Programming Interface used for communication between components.

### Sequence Diagram
A diagram showing interaction flow between systems over time.

### Non-Functional Requirement (NFR)
A quality attribute such as security, performance, scalability, reliability, availability, or maintainability.

### Security Requirement
A requirement related to authentication, authorization, confidentiality, integrity, or auditing.

---

## Development Terms

### Source Code
Application code maintained in version control.

### Repository
A source control location containing code, configuration, and documentation.

### Branch
An isolated line of development.

### Pull Request (PR)
A request to review and merge code changes.

### Code Review
Peer validation of implementation quality and standards.

### Refactoring
Improving internal code structure without changing functionality.

### Technical Debt
Future cost caused by implementation shortcuts.

---

## DevOps Terms

### CI (Continuous Integration)
Practice of automatically building and validating code changes.

### CD (Continuous Delivery/Deployment)
Practice of automatically releasing verified changes.

### Pipeline
Automated workflow for build, test, security validation, and deployment.

### Infrastructure as Code (IaC)
Provisioning infrastructure through code instead of manual processes.

### Environment
A deployment stage such as Development, QA, UAT, or Production.

### Release
A deployable version of the solution.

### Rollback
Restoration of a previous stable release.

---

## Quality Assurance Terms

### Test Case
A set of steps used to validate expected behavior.

### Test Scenario
A high-level validation objective.

### Positive Test
Validates expected successful behavior.

### Negative Test
Validates error handling and failure conditions.

### Edge Case
Validation of uncommon or boundary conditions.

### Defect
A deviation between expected and actual behavior.

### Regression Testing
Testing to ensure existing functionality remains unaffected.

### Traceability Matrix
Mapping between requirements, acceptance criteria, test cases, and defects.

---

## Agentic AI Terms

### Orchestrator Agent
Coordinates execution across multiple specialized agents.

### BA Agent
Creates and validates business requirements, user stories, acceptance criteria, assumptions, and scope.

### Architect Agent
Generates architecture designs, integrations, NFRs, and technical decisions.

### Developer Agent
Generates implementation artifacts, code, APIs, and technical documentation.

### DevOps Agent
Creates deployment pipelines, IaC templates, release strategies, and operational configurations.

### QA Agent
Generates test scenarios, test cases, traceability, and validation reports.

### MCP Server
Model Context Protocol server that exposes tools, instructions, validations, repositories, and enterprise systems to AI agents.

### Instruction File
Markdown document containing execution guidance, rules, workflow steps, and constraints.

### Validation File
Markdown document containing quality gates and verification rules.

### Skill
A reusable capability that an agent can invoke to perform a specific task.

### Tool
An external capability available to an agent through APIs, MCP, workflows, or custom integrations.

### Guardrail
A rule that prevents unsafe, non-compliant, or invalid AI actions.

### Human Approval Gate
A required human validation step before execution can proceed.

---

## Agile Delivery Terms

### Sprint
A time-boxed delivery iteration.

### Backlog
Prioritized list of work items.

### Story Points
Relative effort estimation for a user story.

### Definition of Ready (DoR)
Criteria that must be met before work begins.

### Definition of Done (DoD)
Criteria that must be met before work is considered complete.

### Velocity
Amount of work completed during a sprint.

### Increment
A completed and potentially releasable outcome of a sprint.

---

## Recommended Status Values

### User Story Status
- Draft
- Ready for Review
- Approved
- Ready for Development
- In Progress
- In Testing
- UAT
- Done
- Closed

### Defect Status
- New
- Assigned
- In Progress
- Fixed
- Retest
- Closed
- Rejected
- Deferred

