# Test Implementation Plan Template

## Overview
- **Feature**: [Feature being tested]
- **Issue**: #[Issue number]
- **Total Scenarios**: [Number]
- **Test Framework**: [Framework to use]
- **TDD Phase**: RED (Tests must fail initially)

## Test Framework Selection

### Chosen Framework: [Framework Name]
- **Reason**: [Why this framework]
- **Version**: [Version number]
- **Dependencies**: [Required packages]

### Installation Commands
```bash
# Commands to install test framework
[installation commands]
```

## Test Structure

### Directory Organization
```
tests/
├── unit/
│   ├── test_[feature]_[component].ext
│   └── test_[feature]_[service].ext
├── integration/
│   └── test_[feature]_integration.ext
├── fixtures/
│   └── [feature]_fixtures.ext
└── helpers/
    └── test_helpers.ext
```

### Naming Conventions
- **Test Files**: `test_[feature]_[aspect].ext`
- **Test Functions**: `test_[what]_[condition]_[expected]`
- **Test Classes**: `Test[FeatureName][Aspect]`

## Test Categories

### 1. Unit Tests
Tests for individual functions/methods in isolation.

| Component | Function | Test Count | Priority |
|-----------|----------|------------|----------|
| [Component1] | [function1] | [3] | High |
| [Component2] | [function2] | [2] | Medium |

### 2. Integration Tests
Tests for component interactions.

| Integration Point | Components | Test Count | Priority |
|-------------------|------------|------------|----------|
| [API endpoint] | [A + B] | [2] | High |
| [Database] | [Service + DB] | [3] | High |

### 3. Edge Case Tests
Tests for boundary conditions.

| Edge Case | Description | Test Count | Priority |
|-----------|-------------|------------|----------|
| [Empty input] | [Handle empty data] | [1] | Medium |
| [Max values] | [Handle limits] | [1] | Low |

### 4. Error Tests
Tests for error conditions.

| Error Type | Trigger | Expected Response | Test Count |
|------------|---------|-------------------|------------|
| [Validation] | [Invalid input] | [Error message] | [2] |
| [Not found] | [Missing resource] | [404 error] | [1] |

## Test Implementation Details

### Test Data/Fixtures
```[language]
// Example test data structure
[test data example]
```

### Mock/Stub Requirements
- **External Service [X]**: Mock API responses
- **Database**: Use in-memory database
- **File System**: Mock file operations

### Test Helpers
```[language]
// Common test utilities
[helper functions]
```

## Expected Test Results

### Initial State (RED Phase)
All tests MUST fail because:
- [ ] Function [X] doesn't exist yet
- [ ] Class [Y] not implemented
- [ ] API endpoint [Z] not created
- [ ] Feature code not written

### Failure Messages Expected
- `[Function] is not defined`
- `Cannot find module [module]`
- `404 - Endpoint not found`
- `Method [method] does not exist`

## Test Execution Plan

### Phase 1: Write Basic Tests
1. Create test file structure
2. Write happy path tests
3. Verify tests fail correctly

### Phase 2: Add Edge Case Tests
1. Add boundary condition tests
2. Add empty/null input tests
3. Verify all fail appropriately

### Phase 3: Add Error Tests
1. Write error condition tests
2. Add validation tests
3. Confirm failure reasons

### Phase 4: Integration Tests
1. Write component interaction tests
2. Add API/database tests
3. Ensure proper failures

## Test Commands

### Run All Tests
```bash
[command to run all tests]
```

### Run Specific Category
```bash
[command for unit tests]
[command for integration tests]
```

### Generate Coverage Report
```bash
[coverage command]
```

## Coverage Goals

| Metric | Target | Current | Status |
|--------|--------|---------|--------|
| Line Coverage | 80% | 0% | ❌ |
| Branch Coverage | 75% | 0% | ❌ |
| Function Coverage | 90% | 0% | ❌ |

## Success Criteria

### For This Phase (RED)
- [ ] All test files created
- [ ] All tests are failing
- [ ] Failures are due to missing implementation
- [ ] No syntax errors in tests
- [ ] Tests are runnable

### For Next Phase (GREEN)
- [ ] All tests will pass
- [ ] No test modifications needed
- [ ] Implementation satisfies all assertions

## Risk Assessment

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| [Complex mocking] | Medium | High | [Use simple stubs] |
| [Test dependencies] | Low | Medium | [Isolate tests] |

## Notes
- Tests define the contract for implementation
- Do not implement functionality, only tests
- Clear failure messages guide implementation
- Tests must be independent and repeatable

## Next Steps
After tests are written and failing:
1. Tag @claude_implementor to write code
2. Implementation will make tests pass
3. No changes to tests during implementation