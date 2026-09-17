# Business Analyst Validation Rules


## 1. Validation Objective


Validate that every Business Analyst output is:


- Complete

- Clear

- Testable

- Traceable

- Business-focused

- Free from unsupported assumptions

- Ready for downstream architecture, development, and QA activities


## 2. Blocking Validation Rules


The output must fail validation if any blocking rule is violated.


### BA-001: Persona Is Required


The user story must identify a specific user, business role, or system persona.


Invalid:


As a user, I want a report.


Valid:


As a regional sales manager, I want to view monthly territory performance so

that I can identify regions requiring corrective action.


### BA-002: Capability Is Required


The story must describe a clear capability or action.


The capability must not be empty, vague, or limited to a technical component.


### BA-003: Business Outcome Is Required


The `so that` section must describe a meaningful business or user outcome.


Invalid:


So that the feature works.


Valid:


So that I can identify delayed orders before they affect customer commitments.


### BA-004: Acceptance Criteria Are Required


Every user story must contain at least one acceptance criterion.


Do not assume a fixed number unless the requirement or template explicitly

specifies one.


### BA-005: Given-When-Then Structure


Every acceptance criterion must include:


- Given: Initial context or precondition

- When: User or system action

- Then: Verifiable result


### BA-006: Acceptance Criteria Must Be Testable


Reject criteria containing unmeasurable descriptions such as:


- Quickly

- Easily

- Seamlessly

- User-friendly

- Appropriate

- Optimized

- High performance


Such wording is permitted only if a measurable definition is provided by an

approved source.


### BA-007: No Fabricated Information


The output must not invent:


- Dates

- Amounts

- Thresholds

- User identities

- Project values

- System names

- Compliance requirements

- Performance targets

- Approval levels

- External dependencies


### BA-008: Story Scope Must Be Cohesive


A single story must not combine unrelated capabilities or independent business

outcomes.


If unrelated outcomes exist, recommend decomposition.


### BA-009: Tool Action Requires Mandatory Fields


Do not call an external create or update tool unless all tool-mandatory fields

are available.


### BA-010: Creation Must Be Confirmed by Tool Result


Do not claim successful creation unless the external tool returns:


- Successful status

- Work item identifier

- Work item URL or equivalent reference


## 3. Warning Rules


Warnings do not necessarily block the output, but they must be disclosed.


### BA-W001: Generic Persona


Raise a warning when the persona is `user`, `customer`, or `administrator`

without further context.


### BA-W002: Missing Business Rules


Raise a warning if the requirement appears to contain business decisions but

no business rules are available.


### BA-W003: Missing Error Scenario


Raise a warning when only a successful scenario is covered and an error

condition is reasonably applicable.


Do not invent the error condition. Identify it as an open question.


### BA-W004: Missing Dependency Information


Raise a warning when the requirement references an external application,

service, data source, or approval process but dependency details are missing.


### BA-W005: Non-Functional Requirement Is Unspecified


Raise a warning when security, performance, availability, privacy, or

accessibility appears relevant but no measurable requirement is provided.


## 4. Validation Response Format


Return validation in this structure:
 
