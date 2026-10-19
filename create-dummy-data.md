---
name: create-dummy-data
description: Generate comprehensive, validated test data from any output specification, schema, or data format. Automatically analyse output structures and produce representative, realistic test data with edge case coverage. Use this skill whenever the user needs to create test data, mock data, or synthetic datasets for development, testing, QA, API mocking, database seeding, UI testing, or load testing scenarios. Triggers on requests to generate test fixtures, sample records, dummy data, seed databases, mock APIs, or create data that validates a given output format.
trigger_phrases:
  - "generate test data"
  - "create dummy data"
  - "create test data"
  - "generate mock data"
  - "mock this API"
  - "seed the database"
  - "test data for this format"
  - "what data would produce this output?"
  - "generate sample records"
  - "create test fixtures"
  - "create synthetic data"
  - "generate fixture data"
  - "create sample dataset"
  - "generate test fixtures"
  - "seed test data"
  - "mock data for"
  - "create example data"
  - "generate example records"
  - "populate this template"
  - "fill in this template with dummy data"
  - "create sample data for this structure"
  - "recreate this template with data"
  - "what data would complete this template?"
  - "dummy data that matches this structure"
version: "1.0"
author: Claude
compatibility: "Claude 3.5+"
tags:
  - testing
  - data generation
  - test fixtures
  - mock data
  - QA
  - development
  - API testing
  - database seeding
  - synthetic data
  - test automation
---

# Create Dummy Data Skill

Generate comprehensive, validated test data from any output specification or data format. Automatically analyse desired output structures and produce representative test data with full edge case coverage.

---

## Skill Overview

**Purpose:** Transform output specifications into intelligent, realistic test data that validates all requirements and edge cases.

**Core Value:** Skip manual test data creation. Provide your desired output format, and receive complete test data with analysis of what's required, field classifications, edge cases, and validation guidance.

**Use When:** You need test data for development, testing, QA, API mocking, database seeding, UI component testing, or load testing scenarios.

---

## Triggers

This skill activates when the user:

- Asks to generate test data, dummy data, mock data, or sample data
- Wants to create test fixtures or test datasets
- Needs to seed a database or populate a test environment
- Is developing an API and needs sample payloads
- Wants to test report formats or data structures
- Asks for data that "recreates" or "validates" a given output
- Mentions generating data from a schema, format, or specification
- Requests "edge cases" or "boundary test data"
- Wants realistic but synthetic data for testing purposes

Trigger phrases include: "generate test data", "create dummy data", "mock this API", "seed the database", "test data for this format", "what data would produce this output?", "generate sample records"

Do NOT trigger when: The user is asking for data analysis, real data extraction, or privacy-sensitive production data handling (unless explicitly framed as test data generation).

---

## Skill Process

### Step 1: Accept Output Specification

The user provides one of:

- Example output (JSON, CSV, database record, API response)
- Schema or format definition (field list, data model, specification)
- Current output they want to recreate or test
- Real or expected API response
- Database export sample
- Report layout or structure

### Step 2: Analyse the Output

Examine:

- Structure, fields, data types, and relationships
- All required and optional fields
- Constraints, patterns, or embedded business rules
- Field dependencies and calculated relationships
- Enumerated or conditional values

### Step 3: Classify Data Elements

For each field, determine:

- **Essential:** Required to produce output
- **Conditional:** Required only under specific conditions
- **Enhancement:** Optional, improves quality
- **Metadata:** Supporting information

**Template Fidelity Note:** When populating formal templates (charters, specifications, compliance documents), separate definitive dummy data (which must exactly match template structure) from contextual guidance (which is advisory only).

### Step 4: Identify Edge Cases and Variations

Consider:

- Boundary values (minimum, maximum, zero)
- Missing or null values
- Empty strings or arrays
- Negative numbers (where inappropriate)
- Very large or very small numbers
- Special characters
- Unusual but valid combinations
- Enumerated value coverage
- Relationship violations or dependencies

### Step 5: Generate Test Data

Create 3-10 representative test records that:

- Exercise all identified requirements
- Include edge cases and boundaries
- Remain realistic and representative
- Vary across all possible output ranges
- Can be directly used in testing or mocking

### Step 6: Deliver Results

For general test data requests, provide structured output including:

- Output analysis summary
- Identified data requirements
- Field breakdown table
- Edge cases and variations list
- Representative test data (3-10 examples)
- Validation notes and usage guidance

For template population requests, deliver:

- **Primary Deliverable:** Definitive dummy data structured exactly as the template specifies (template sections only, no supplementary content unless requested)
- **Optional Secondary Deliverable:** Contextual guidance clearly separated and marked as advisory only

Never confuse definitive template data with advisory content.

---

## Delivery Structure

```
## Output Analysis Summary
[Brief description of what was analysed]

## Identified Requirements
[List of what information is needed]

## Field Breakdown
| Field Name | Type | Required? | Constraints | Classification |
| - | - | - | - | - |

## Edge Cases and Variations
[List of edge cases that should be tested]

## Test Data (X representative examples)
[Generated test data in requested format]

## Validation Notes
[How to verify the test data is correct]

## Usage Guidance
[How to apply this test data]
```

---

## Template Fidelity Principle

When generating dummy data for formal templates (charters, specifications, compliance documents), critical distinction applies:

### Core Rule

Output must be immediately testable against the template structure. This means:

- Definitive data must align exactly with what the template specifies
- No supplementary sections should be added unless explicitly requested
- Advisory content must be clearly separated from template elements

### Classification: Definitive vs. Advisory

**Definitive Template Elements:**
- Sections explicitly called for in the template
- Fields required by the template structure
- Data that directly fills template placeholders
- Immediately usable without interpretation

**Advisory/Contextual Guidance:**
- Supplementary explanations
- How to interpret or apply template data
- Best practice notes
- Examples beyond the template scope

### When to Separate

If both are needed:

1. **Primary Section:** Template only with dummy data
2. **Clearly Marked Separate Section:** Advisory guidance with label "Optional Guidance" or "Contextual Notes"

**Red Flags for Confusion:**
- Mixing template sections with explanatory notes
- Adding supplementary sections without explicit request
- Unclear which content is definitive vs. advisory
- Template data that requires interpretation to use

### Example Pattern

**User provides:** Initiative Charter template structure

**Correct Response:**
- Template with definitive dummy data only
- No separate guidance section (unless user asks: "Also provide guidance")

**Incorrect Response:**
- Template data plus unrequested guidance sections
- Mixed advisory notes within template sections
- Unclear what should actually fill the template

---

## Output Format Options

Ask the user their preference or infer from context:

- **JSON** (array of objects or newline-delimited)
- **CSV** (with headers)
- **SQL** (INSERT statements)
- **Python** (list of dictionaries)
- **JavaScript** (array of objects)
- **YAML** (structured format)
- **XML** (with schema)
- Same format as original output (direct comparison)

Default to the user's original format if they provide one.

---

## Advanced Capabilities

### Relationship Detection

Identify and test:

- Calculated fields (total = quantity × price)
- Dependent fields (status values depend on date)
- Foreign key relationships (must exist in reference table)
- Conditional logic (discount applies only if threshold met)

### Realistic Variation

Generate test data that:

- Reflects real-world distributions
- Includes common and uncommon cases
- Tests all enumerated values
- Covers different time periods or geographic regions
- Represents category diversity

### Constraint Enforcement

Respect:

- Data type requirements (int, decimal, string, date)
- Value ranges (minimum, maximum, enumerated sets)
- Format requirements (email, phone, ISO 8601 dates)
- Length constraints (max string length)
- Precision requirements (decimal places)

---

## Usage Examples

### Example 1: API Response

**User Input:**
```json
{
  "transactionId": "txn_12345678",
  "amount": 159.99,
  "currency": "AUD",
  "status": "completed",
  "timestamp": "2024-07-15T14:32:00Z",
  "metadata": {
    "source": "mobile_app",
    "userId": "user_987"
  }
}
```

**Skill Output:**
- Identifies that transactionId requires UUID format
- Amount must be positive decimal with 2 places
- Currency uses ISO 4217 codes
- Status is enumerated (completed, pending, failed, etc.)
- Timestamp requires ISO 8601 format
- Generates 5 transactions with different statuses, amounts, and metadata variations

### Example 2: CSV Report

**User Input:**
```
Date,Product,Quantity,Price,Total,Region
2024-07-15,Widget A,5,12.50,62.50,Sydney
2024-07-15,Widget B,3,8.99,26.97,Melbourne
```

**Skill Output:**
- Date format: YYYY-MM-DD
- Product: string, varying length
- Quantity: positive integer
- Price: decimal with 2 places
- Total: calculated field (Quantity x Price)
- Region: enumerated (Sydney, Melbourne, etc.)
- Generates 8-10 rows including edge cases (zero quantity, high volumes, boundary prices)

### Example 3: Database Schema

**User Input:**
```sql
CREATE TABLE orders (
  id INT PRIMARY KEY,
  customer_id INT NOT NULL,
  order_date TIMESTAMP,
  total_amount DECIMAL(10,2),
  status ENUM('pending','confirmed','shipped','delivered')
);
```

**Skill Output:**
- Generates SQL INSERT statements with valid data
- Includes all status values
- Respects auto-increment for id
- Covers edge cases (zero total, old dates, various statuses)
- Provides 6-8 representative orders

### Example 4: Template Population

**User Input:**
Initiative Charter template structure with sections:
- Charter Header (ID, Name, Sponsor, Approved Date)
- Governance (RACI matrix, Approvers)
- Objectives (Strategic alignment, Success criteria)
- Scope (In-scope, Out-of-scope)

**Skill Output:**
- Complete template populated with definitive dummy data only
- All required sections filled with realistic examples
- No supplementary guidance sections added
- Data is ready to use immediately in the template

**Note:** If user requests guidance after receiving the template: Provide separate "Optional Guidance" section with explanations, without changing the definitive template data.

---

## Best Practices

### Provide Complete Context

Share:
- Multiple examples (shows variation)
- Real or realistic data (reveals constraints)
- Known edge cases or validation rules
- Business rules or relationships

### Be Specific About Use

Tell the skill:
- What this data will test (UI, API, database, load test)
- What scenarios matter most
- Any known problem areas
- Performance or scale requirements

### Specify Output Format

Indicate preferred delivery format:
- JSON for APIs
- CSV for reports or spreadsheets
- SQL for database seeding
- Language-specific (Python, JavaScript) for code integration

### Request Scale if Needed

For different volumes:
- "3-5 examples" for quick validation
- "10-15 records" for comprehensive testing
- "100+ records" for load testing
- "Variations across all edge cases" for exhaustive coverage

---

## Validation Checklist

After receiving test data, verify:

- All required fields are present
- Data types match specification
- Values respect constraints and ranges
- Edge cases are represented
- Relationships between fields are logically correct
- Calculated fields are accurate
- Enumerated values cover all options
- Data is realistic and representative
- Volume is sufficient for intended testing
- Data can actually produce the intended output

---

## Integration Patterns

### With APIs

Use generated test data for:
- Request/response contract testing
- API mocking and stubbing
- Integration tests
- Postman/Insomnia collections

### With Databases

Use generated test data for:
- Database seeding
- Development environment population
- Migration validation
- Schema testing

### With UI Components

Use generated test data for:
- Component rendering tests
- Validation and error state testing
- Accessibility testing
- Visual regression testing

### With Load Testing

Use generated test data for:
- JMeter, Gatling, or k6 scenarios
- Performance testing with realistic volume
- Scalability validation
- Stress testing

---

## Prompt Variations

### Quick Analysis Only

Request analysis without generation:
"Analyse this output specification and identify all required test data elements. Do not generate test data yet. Focus on field classification, data types, constraints, relationships, and edge cases."

### Maximum Coverage

Request comprehensive test suite:
"Generate test data covering all normal conditions, edge cases, boundary conditions, error states, and performance scenarios. Include at least 10-15 representative cases focusing on [specific concern]."

### Specific Scenario

Request context-focused data:
"Generate test data specifically for [UI testing/API testing/load testing]. Focus on edge cases relevant to [specific concern]."

---

## Tips for Best Results

- Provide real or realistic examples, not abstract descriptions
- Include multiple samples to show variation patterns
- Mention any known constraints or business rules
- Specify the intended use (what are you testing?)
- Request the output format that best fits your workflow
- Ask for scale appropriate to your testing needs (3 examples vs. 100 records)

---

## Key Learning: Template Population Distinction

**Insight from Initiative Charter engagement (16 July 2026):**

When populating formal templates with dummy data, there is a critical distinction between definitive and advisory content:

**The Problem:** Mixing template data with contextual guidance blurs boundaries, making it unclear what should actually fill the template vs. what is explanatory.

**The Solution:** Strict separation of concerns:
- Definitive data: Only what the template structure requires
- Advisory guidance: Clearly separated, marked as optional, delivered only when requested

**When This Matters Most:**
- Formal compliance documents
- Governance charters
- Contract templates
- Specification documents
- Any template where output fidelity is critical

**Application Principle:**
- Test: Can someone use this data directly in the template without interpretation?
- If not: You have mixed definitive and advisory content


