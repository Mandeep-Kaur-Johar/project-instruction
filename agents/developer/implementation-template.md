# Developer Implementation Template

## Purpose

Use this template to generate a complete implementation package for a User Story or a logically grouped set of User Stories.

## Implementation Context

- **Project:** `<projectName>`
- **Repository:** `<repositoryName>`
- **Epic:** `<epicId> - <epicTitle>`
- **Feature:** `<featureId> - <featureTitle>`
- **User Story:** `<userStoryId> - <userStoryTitle>`
- **Target Branch:** `feature/story-<userStoryId>`
- **Architecture Root:** `docs/architecture/epic-<epicId>/`

## Required Workflow

1. Retrieve the Epic hierarchy.
2. Retrieve the relevant Feature and User Story details.
3. Retrieve all Acceptance Criteria.
4. List the repository tree.
5. Read the System Design Document and relevant architecture text files.
6. Determine whether application source code already exists.
7. If source code exists, extend the existing structure and conventions.
8. If source code does not exist, create a complete application scaffold in the same repository.
9. Generate implementation files in logical batches.
10. Commit each batch to the story branch.
11. Generate tests and the GitHub Actions workflow.
12. Perform a consistency review across frontend, backend, tests, and configuration.
13. Create one draft pull request after all batches are committed.
14. Return branch, commit, changed-file, pull-request, and validation details.

## Architecture-Only Repository Rule

If the repository contains only architecture documents:

- Treat the repository as writable and valid for implementation.
- Treat the architecture artifacts and Azure DevOps requirements as the source of truth.
- Create the application scaffold directly in the existing repository.
- Do not stop, ask for a different repository, or require an existing scaffold.

## Default Solution Structure

Adapt this structure when the architecture specifies different names or boundaries.

```text
/
├── .github/
│   └── workflows/
│       └── ci.yml
├── docs/
│   ├── architecture/
│   │   └── epic-<epicId>/
│   └── IMPLEMENTATION.md
├── src/
│   ├── api/
│   │   ├── <SolutionName>.Api/
│   │   ├── <SolutionName>.Application/
│   │   ├── <SolutionName>.Domain/
│   │   └── <SolutionName>.Infrastructure/
│   └── web/
│       ├── src/
│       │   ├── api/
│       │   ├── components/
│       │   ├── features/
│       │   ├── hooks/
│       │   ├── models/
│       │   ├── pages/
│       │   ├── routes/
│       │   └── tests/
│       ├── package.json
│       ├── tsconfig.json
│       └── vite.config.ts
├── tests/
│   ├── <SolutionName>.UnitTests/
│   └── <SolutionName>.IntegrationTests/
├── <SolutionName>.sln
├── .gitignore
└── README.md
```

## Backend Requirements

Generate, as required by the architecture:

- .NET 8 solution and project files
- API entry point and dependency registration
- Controllers or minimal API endpoints
- Application services and interfaces
- Domain entities and value objects
- Request and response contracts
- Persistence configuration and migrations strategy
- Authentication and authorization
- External integration clients
- Validation and error handling
- Logging, health checks, and observability hooks
- Unit and integration tests

All generated backend files must contain complete implementation content. Do not use placeholder comments in place of required behavior.

## Frontend Requirements

Generate, as required by the architecture:

- React TypeScript application scaffold
- Routing and protected routes
- Pages and reusable components
- API client and typed contracts
- Authentication/session handling
- Forms and client-side validation
- Loading, empty, success, and error states
- Configuration handling
- Unit and component tests

All backend API paths and frontend client calls must be consistent.

## Configuration Requirements

Generate applicable configuration files, including:

- `.gitignore`
- Application settings templates without secrets
- Frontend environment template without secrets
- Package and TypeScript configuration
- Build and test configuration
- GitHub Actions workflow
- Developer setup documentation

## Logical Commit Batches

Use manageable batches rather than one oversized tool call.

### Batch 1: Foundation

- Solution and project files
- Package configuration
- Shared configuration
- Application entry points

### Batch 2: Backend Domain and Infrastructure

- Domain models
- Persistence
- Repositories
- External integration foundations

### Batch 3: Backend Application and API

- Services
- Contracts
- Validation
- Endpoints
- Authorization

### Batch 4: Frontend Foundation

- React scaffold
- Routing
- API client
- Shared models
- Authentication/session foundation

### Batch 5: Frontend Features

- Pages
- Feature components
- Forms
- User flows
- Error handling

### Batch 6: Tests

- Backend unit tests
- Backend integration tests
- Frontend unit/component tests
- Acceptance Criteria coverage

### Batch 7: Delivery

- CI workflow
- README
- Implementation traceability document
- Final consistency fixes

## Traceability Document

Generate `docs/IMPLEMENTATION.md` with:

- Epic, Feature, and User Story IDs
- Architecture files used
- Acceptance Criteria mapping
- Implementation file mapping
- Test mapping
- Known limitations
- Validation status

## Pull Request Template

```markdown
## Traceability

- Epic: <epicId>
- Feature: <featureId>
- User Story: <userStoryId>

## Requirement Summary

<requirementSummary>

## Acceptance Criteria

- <acceptanceCriterion1>
- <acceptanceCriterion2>

## Architecture Files

- <architecturePath1>
- <architecturePath2>

## Implementation Summary

- <backendSummary>
- <frontendSummary>
- <testSummary>
- <deliverySummary>

## Validation

- Status: CI pending
- Build: Not claimed until confirmed by CI
- Tests: Not claimed until confirmed by CI
```

## Required Final Result

Return a structured summary containing:

- Repository name
- Feature branch
- Commit SHA or commit SHAs
- Number and paths of changed files
- Draft pull request URL, when created
- Exact pull-request error, when creation fails
- Validation status
- Remaining limitations, if any

Never report successful implementation unless source files were committed successfully.
