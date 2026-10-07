# Developer Agent Validation Rules

## Purpose

Validate generated implementation work before reporting completion or opening a draft pull request.

## Required Inputs

The Developer Agent must validate implementation against:

- Epic hierarchy
- Feature details
- User Story details
- Acceptance Criteria
- System Design Document
- Referenced architecture artifacts
- Existing repository conventions, when application source code already exists

## Repository Rules

- An architecture-only repository is a valid implementation target.
- Absence of an existing application source tree must not block implementation.
- When source code does not exist, create a new React TypeScript and .NET 8 scaffold in the existing repository.
- Never commit generated implementation directly to `main`.
- Use a branch named `feature/story-<userStoryId>` unless the repository defines another approved convention.
- Do not request another repository solely because the current repository contains architecture deliverables only.

## Traceability Validation

Before completion, verify that:

- Every generated implementation batch identifies the Epic, Feature, and User Story.
- Every Acceptance Criterion is mapped to implementation files.
- Every Acceptance Criterion has at least one validation method, automated test, or documented manual verification step.
- Architecture decisions used by the implementation are traceable to the relevant architecture files.
- Unimplemented Acceptance Criteria are clearly reported and must not be represented as complete.

## Backend Validation

For the .NET 8 backend, verify that:

- The solution and project files are present.
- The application entry point and dependency registration are present.
- Required API endpoints, services, domain models, persistence components, and integrations are implemented.
- Configuration values use configuration providers or environment variables rather than embedded secrets.
- Authorization is enforced server-side.
- Input validation and consistent error handling are implemented.
- Logging excludes secrets, credentials, tokens, and sensitive payloads.
- Unit and integration test projects are included where required.

## Frontend Validation

For the React TypeScript frontend, verify that:

- `package.json`, TypeScript configuration, and build configuration are present.
- Application entry points, routing, pages, components, services, and models are present.
- API calls match the backend routes and request/response contracts.
- Protected functionality is guarded in the user interface, while server-side authorization remains authoritative.
- Loading, empty, success, and error states are handled.
- Frontend tests are included for important user flows and reusable logic.

## Security Validation

Verify that:

- No passwords, API keys, connection strings, tokens, or private certificates are committed.
- Authentication and authorization follow the architecture requirements.
- User-controlled input is validated.
- Sensitive operations are auditable where required.
- Error responses do not reveal secrets or internal implementation details.
- Generated dependencies are limited to those needed by the implementation.

## Test and Build Status

- Generate the required tests and CI workflow.
- Do not claim that builds, tests, linting, coverage, or security scans passed unless a tool or CI result explicitly confirms success.
- If build tools are unavailable, report validation as `CI pending`.
- A self-review may identify likely issues, but self-review must not be represented as successful compilation or test execution.

## Tool Execution Rules

- Read architecture text files with the repository file-reading tool, not only the repository tree tool.
- Do not stop after listing repository paths when relevant architecture files are available.
- Generate implementation files in manageable logical batches.
- Use `commit_files` repeatedly when a complete solution is too large for one tool call.
- Use `commit_generated_implementation` only when the full `files` payload is already available and within tool limits.
- After all implementation batches are committed, create one draft pull request.
- Do not ask for confirmation between ordinary implementation batches when the user already requested implementation and commit.

## Completion Criteria

Implementation may be reported as generated only when:

- Required source files have been committed to the feature branch.
- The commit result contains a successful commit SHA.
- The changed file paths correspond to the intended implementation.
- A draft pull request was created, or the exact pull-request failure was reported without claiming that a pull request exists.
- Validation status is stated accurately as confirmed by CI or `CI pending`.

## Failure Handling

If a tool call fails:

- Report the exact failed operation and returned error.
- Preserve successful commits already made to the feature branch.
- Retry only when the failure is recoverable and retrying will not duplicate or corrupt work.
- Do not replace a tool failure with a fabricated success response.
