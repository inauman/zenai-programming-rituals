# 🧪 ZenAI Test Strategy

## Overview

This document defines the universal test strategy for all ZenAI projects, emphasizing **automation-first**, **test-cases-as-documentation**, and **shift-left testing** principles. The strategy is designed to work across all application types (desktop, web, mobile) and technology stacks.

## 🏗️ Two-Phase Test Pyramid

### Phase 1: Pre-Release Development Pyramid
```
        🔺 E2E Tests (Critical user workflows)
       🔺🔺 Integration Tests (Module/component interactions)  
    🔺🔺🔺 Unit Tests (Function/component level)
```

### Phase 2: Post-Production Deployment
```
        🔺 Smoke Tests (Health check validation)
       🔺🔺 E2E Tests (Critical user workflows)
      🔺🔺🔺 Integration Tests (Module interactions)  
   🔺🔺🔺 Unit Tests (Function/component level)
```

## 🎯 Core Principles

### 1. Test-Cases-as-Documentation
- **Descriptive Names**: `should_encrypt_file_with_valid_key_and_passphrase()`
- **Given-When-Then Structure**: Clear test flow documentation
- **Business Logic Focus**: Tests reflect user scenarios and requirements
- **Living Documentation**: Tests serve as executable specifications

### 2. Shift-Left Testing
- **Early Validation**: Test as early as possible in development cycle
- **Prevention Over Detection**: Catch issues before they reach production
- **Continuous Feedback**: Immediate test results during development
- **Quality Gates**: Automated validation before any deployment

### 3. Automation-First
- **Zero Manual Testing**: All tests must be automated
- **CI/CD Integration**: Tests run automatically on every change
- **Parallel Execution**: Optimize for speed and efficiency
- **Deterministic Results**: No flaky tests, consistent outcomes

## 📁 Standard Test Organization

### Hierarchical Structure
```
tests/
├── common/                    # Shared test utilities
│   ├── mod.rs                # Test suite setup/teardown
│   ├── fixtures.rs           # Test data factories
│   └── helpers.rs            # Common test helpers
├── unit/                     # Unit tests (many)
│   ├── mod.rs                # Unit test suite runner
│   └── [module]/             # Organized by module
├── integration/              # Integration tests (some)
│   ├── mod.rs                # Integration test suite runner
│   └── workflows/            # End-to-end workflows
├── e2e/                      # E2E tests (few)
│   └── critical_flows/       # Critical user journeys
└── smoke/                    # Smoke tests (health checks)
    └── mod.rs                # Smoke test suite runner
```

### Naming Conventions
- **Unit Tests**: `[module]_tests.rs`
- **Integration Tests**: `[module]_integration_tests.rs`
- **E2E Tests**: `[workflow]_e2e_tests.rs`
- **Smoke Tests**: `[component]_smoke_tests.rs`

## 🛠️ Framework Selection Guidelines

### Rust Backend
- **Unit Tests**: Rust's built-in `#[cfg(test)]` + `cargo test`
- **Integration Tests**: Rust's standard integration test framework
- **Test Organization**: `rstest` for parameterized tests and fixtures
- **Mocking**: `mockall` for dependency mocking
- **Test Data**: `tempfile` for temporary file management
- **Assertions**: `assert2` for better assertion messages

### React Frontend
- **Unit Tests**: Jest + React Testing Library
- **Component Tests**: @testing-library/react + @testing-library/jest-dom
- **Mocking**: jest.mock() for module mocking
- **Test Data**: @testing-library/user-event for user interactions
- **E2E Tests**: Playwright (industry standard)

### Python Backend
- **Unit Tests**: pytest
- **Integration Tests**: pytest with fixtures
- **Mocking**: unittest.mock or pytest-mock
- **Test Data**: pytest-factoryboy for test data factories

### Java Backend
- **Unit Tests**: JUnit 5
- **Integration Tests**: Spring Boot Test
- **Mocking**: Mockito
- **Test Data**: TestContainers for external dependencies

## 🎭 Test Quality Standards

### 1. Eliminate Test Flakiness
- **Isolated Test Data**: Each test creates its own temporary data
- **Parallel-Safe**: Use unique identifiers and temp directories
- **Deterministic**: No shared state between tests
- **Cleanup**: Automatic teardown after each test
- **No External Dependencies**: Mock external services and APIs

### 2. Parallel Execution Optimization
- **Independent Tests**: No test dependencies or shared state
- **Resource Isolation**: Separate temp directories per test
- **Fast Execution**: Unit tests < 100ms each
- **Efficient Setup**: Minimal setup/teardown overhead

### 3. Comprehensive Coverage
- **Happy Path**: Core functionality works as expected
- **Edge Cases**: Boundary conditions and error scenarios
- **Error Conditions**: All error paths are tested
- **Security**: Security-critical paths have dedicated tests
- **Performance**: Critical performance paths are benchmarked

## 📊 Quality Metrics

### Execution Metrics
- **Test Execution Time**: < 30 seconds for full suite
- **Parallel Safety**: 100% parallel execution capability
- **Flakiness Rate**: 0% (deterministic results)
- **Setup Time**: < 5 seconds for test environment

### Coverage Metrics
- **Line Coverage**: > 90% for critical paths
- **Branch Coverage**: > 85% for decision points
- **Function Coverage**: > 95% for all functions
- **Integration Coverage**: All module interactions tested

### Documentation Metrics
- **Test Documentation**: 100% of tests are self-documenting
- **Business Logic Coverage**: All user scenarios represented
- **Edge Case Documentation**: All error conditions explicitly tested

## 🔄 Test Lifecycle

### 1. Test Development
```rust
// Example: Test-Cases-as-Documentation
#[rstest]
#[case("valid_key", "correct_passphrase", true)]
#[case("valid_key", "wrong_passphrase", false)]
#[case("invalid_key", "any_passphrase", false)]
fn should_validate_key_with_passphrase(
    #[case] key_id: &str,
    #[case] passphrase: &str,
    #[case] expected: bool,
) {
    // Given: A key store with test keys
    let key_store = setup_test_key_store();
    
    // When: Validating the key with passphrase
    let result = key_store.validate_key(key_id, passphrase);
    
    // Then: Result matches expected outcome
    assert_eq!(result, expected);
}
```

### 2. Test Execution
- **Local Development**: `cargo test` or `npm test`
- **CI/CD Pipeline**: Automated on every commit
- **Pre-Release**: Full test suite execution
- **Post-Deployment**: Smoke tests for health validation

### 3. Test Maintenance
- **Regular Review**: Monthly test suite review
- **Performance Monitoring**: Track test execution times
- **Coverage Analysis**: Monitor coverage trends
- **Flakiness Detection**: Automated flakiness detection

## 🚀 Implementation Checklist

### Setup Phase
- [ ] Choose appropriate testing frameworks for tech stack
- [ ] Set up test directory structure
- [ ] Configure test runners and CI/CD integration
- [ ] Create test utilities and helpers
- [ ] Establish naming conventions

### Development Phase
- [ ] Write unit tests for all business logic
- [ ] Create integration tests for module interactions
- [ ] Implement E2E tests for critical user workflows
- [ ] Add smoke tests for deployment validation
- [ ] Ensure parallel execution capability

### Quality Phase
- [ ] Eliminate all flaky tests
- [ ] Optimize test execution speed
- [ ] Achieve target coverage metrics
- [ ] Document test strategy and patterns
- [ ] Train team on test practices

## 🎯 Success Criteria

### Immediate Goals
- **Zero Flaky Tests**: All tests produce deterministic results
- **Fast Execution**: Complete test suite runs in < 30 seconds
- **High Coverage**: > 90% coverage for critical paths
- **Clear Documentation**: Tests serve as living documentation

### Long-term Goals
- **Continuous Quality**: Automated quality gates prevent regressions
- **Developer Productivity**: Tests provide fast feedback during development
- **Confidence in Deployments**: Comprehensive test coverage enables safe releases
- **Knowledge Preservation**: Tests document business logic and requirements

## 📚 References

- [Test Pyramid by Martin Fowler](https://martinfowler.com/articles/practical-test-pyramid.html)
- [Testing Library Best Practices](https://testing-library.com/docs/guiding-principles)
- [Rust Testing Guidelines](https://doc.rust-lang.org/book/ch11-00-testing.html)
- [Jest Testing Framework](https://jestjs.io/docs/getting-started)
- [Playwright E2E Testing](https://playwright.dev/)

---

> *"Quality is not an act, it is a habit."* — Aristotle 