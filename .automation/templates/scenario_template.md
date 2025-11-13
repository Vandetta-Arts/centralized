# Test Scenarios Template

## Feature: [FEATURE_NAME]

### Overview
[Brief description of the feature being tested]

## Scenario Categories

### 1. Happy Path Scenarios
Tests for normal, expected usage of the feature.

#### Scenario 1.1: [Basic Success Case]
- **Given**: [Initial conditions/state]
- **When**: [Action performed]
- **Then**: [Expected outcome]
- **Test Data**:
  - Input: [Specific values]
  - Expected Output: [Specific values]

#### Scenario 1.2: [Alternative Success Case]
- **Given**: [Initial conditions/state]
- **When**: [Action performed]
- **Then**: [Expected outcome]
- **Test Data**:
  - Input: [Specific values]
  - Expected Output: [Specific values]

### 2. Edge Cases
Tests for boundary conditions and limits.

#### Scenario 2.1: [Minimum Values]
- **Given**: [Setup with minimum values]
- **When**: [Action with minimum input]
- **Then**: [Expected handling]
- **Test Data**:
  - Input: [Minimum values]
  - Expected Output: [Expected result]

#### Scenario 2.2: [Maximum Values]
- **Given**: [Setup with maximum values]
- **When**: [Action with maximum input]
- **Then**: [Expected handling]
- **Test Data**:
  - Input: [Maximum values]
  - Expected Output: [Expected result]

### 3. Error Scenarios
Tests for error conditions and invalid inputs.

#### Scenario 3.1: [Invalid Input Type]
- **Given**: [Normal setup]
- **When**: [Action with wrong type]
- **Then**: [Error response]
- **Test Data**:
  - Input: [Invalid type example]
  - Expected Error: [Error message]

#### Scenario 3.2: [Missing Required Data]
- **Given**: [Incomplete setup]
- **When**: [Action without required data]
- **Then**: [Validation error]
- **Test Data**:
  - Input: [Missing fields]
  - Expected Error: [Validation message]

#### Scenario 3.3: [Null/Undefined Input]
- **Given**: [Normal setup]
- **When**: [Action with null/undefined]
- **Then**: [Appropriate handling]
- **Test Data**:
  - Input: null/undefined
  - Expected Result: [Default or error]

### 4. Integration Scenarios
Tests for interaction with other components.

#### Scenario 4.1: [External Service Integration]
- **Given**: [External service state]
- **When**: [Action triggering integration]
- **Then**: [Correct integration behavior]
- **Test Data**:
  - External Response: [Mocked response]
  - Expected Result: [Processed result]

#### Scenario 4.2: [Database Interaction]
- **Given**: [Database state]
- **When**: [Action affecting database]
- **Then**: [Database correctly updated]
- **Test Data**:
  - Initial DB State: [Data]
  - Expected DB State: [Updated data]

### 5. Performance Scenarios
Tests for performance requirements.

#### Scenario 5.1: [Response Time]
- **Given**: [Normal load]
- **When**: [Typical action]
- **Then**: [Response within threshold]
- **Performance Criteria**:
  - Maximum Response Time: [X ms]
  - Average Response Time: [Y ms]

#### Scenario 5.2: [Concurrent Users]
- **Given**: [Multiple simultaneous users]
- **When**: [Concurrent actions]
- **Then**: [System handles correctly]
- **Performance Criteria**:
  - Concurrent Users: [Number]
  - Success Rate: [Percentage]

### 6. Security Scenarios
Tests for security requirements.

#### Scenario 6.1: [Authorization Check]
- **Given**: [Unauthorized user]
- **When**: [Attempt restricted action]
- **Then**: [Access denied]
- **Test Data**:
  - User Role: [Unauthorized]
  - Expected Response: [403 Forbidden]

#### Scenario 6.2: [Input Sanitization]
- **Given**: [Normal setup]
- **When**: [Malicious input provided]
- **Then**: [Input sanitized/rejected]
- **Test Data**:
  - Malicious Input: [XSS/SQL injection attempt]
  - Expected Result: [Sanitized or rejected]

## Test Data Sets

### Valid Test Data
```json
{
  "valid_user": {
    "id": 1,
    "name": "Test User",
    "email": "test@example.com"
  },
  "valid_product": {
    "id": 100,
    "name": "Test Product",
    "price": 99.99
  }
}
```

### Invalid Test Data
```json
{
  "invalid_email": "not-an-email",
  "negative_price": -10,
  "empty_string": "",
  "special_characters": "!@#$%^&*()"
}
```

## Acceptance Criteria
- [ ] All happy path scenarios pass
- [ ] All edge cases handled correctly
- [ ] All error scenarios return appropriate errors
- [ ] Integration points work as expected
- [ ] Performance meets requirements
- [ ] Security checks pass

## Notes
- [Any special considerations]
- [Dependencies or prerequisites]
- [Known limitations]