# AGENTS.md

This file provides guidance to agents when working with code in this repository.

## Directory Overview

This is a development environment setup for a Node.js/TypeScript project using Visual Studio Code Dev Containers. The repository currently contains configuration files but no application code, indicating it's either a fresh project template or a starter environment.

**Project Type:** Development Environment Setup / Project Template  
**Primary Technology:** Node.js & TypeScript  
**License:** GNU General Public License v3.0

### `LICENSE`
Standard GNU General Public License v3.0 - all code in this repository is open source under GPL v3 terms.

## Development Workflow

### Initial Setup
1. Open the project in VS Code with Dev Containers extension
2. VS Code will automatically build the container using the devcontainer configuration
3. Bob Shell will be installed automatically via the `postCreateCommand`
4. The environment will be ready for Node.js/TypeScript development

### Project Structure Expectations
Since this is a template/starter environment, typical Node.js/TypeScript project files should be added:
- `src/` - Source code directory
- `tests/` - Test files
- `README.md` - Project documentation

## Agent Guidelines

### Code Development
- Use TypeScript as the primary language (environment is pre-configured)
- Follow Node.js best practices
- Leverage yarn as the package manager 

### Testing
When developing features or fixing bugs, always include appropriate tests:

#### Testing Framework
- Use **Jest** as the primary testing framework

#### Test Organization
- Place unit tests in `tests/unit/`
- Place integration tests in `tests/integration/`
- Place end-to-end tests in `tests/e2e/`
- Use descriptive test file names matching the source file: `example.ts` → `example.test.ts`

#### Running Tests
```bash
# Run all tests
yarn test

# Run tests in watch mode
yarn test --watch

# Run tests with coverage
yarn test --coverage

# Run specific test file
yarn test path/to/example.test.ts
```

#### Test Coverage
- Aim for minimum 70% code coverage for new code
- Use `yarn test --coverage` to generate coverage reports
- Coverage reports will be generated in `coverage/` directory

#### Testing Best Practices
- Write tests before or alongside code (TDD/BDD approach preferred)
- Each test should be independent and isolated
- Use descriptive test names that explain what is being tested
- Follow the AAA pattern: Arrange, Act, Assert
- Mock external dependencies and API calls
- Test both success and failure scenarios
- Include edge cases and boundary conditions

#### Example Test Structure
```typescript
describe('ComponentName', () => {
  describe('methodName', () => {
    it('should return expected result when given valid input', () => {
      const input = 'test';
      const result = methodName(input);
      expect(result).toBe('expected');
    });
    
    it('should throw error when given invalid input', () => {
      expect(() => methodName(null)).toThrow();
    });
  });
});
```

### Documentation
- Keep interaction summaries brief but informative
- Use descriptive filenames for interaction logs
- Update this AGENTS.md file as the project evolves and new patterns emerge
