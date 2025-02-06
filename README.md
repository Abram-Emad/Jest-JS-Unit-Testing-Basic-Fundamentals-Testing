# Jest JS Unit Testing Basics

![Jest](https://img.shields.io/badge/Jest-Unit%20Testing-brightgreen) ![JavaScript](https://img.shields.io/badge/JavaScript-ES6%2B-yellow) ![License](https://img.shields.io/badge/License-MIT-blue)

A comprehensive guide and project template to learn the fundamentals of unit testing in JavaScript using **Jest**. This repository is designed for developers who want to master writing testable code, creating test suites, and leveraging Jest's powerful features like mocking, asynchronous testing, and code coverage analysis.

## 🚀 Project Overview

This project serves as an educational resource for understanding the core concepts of unit testing with Jest. It includes practical examples, test-driven development (TDD) workflows, and real-world testing scenarios to help you:

- Write clean, maintainable unit tests.
- Validate JavaScript functions and modules.
- Handle asynchronous operations and API mocking.
- Measure test coverage and optimize testing strategies.

## ✨ Key Features

- **Basic Assertions**: Test simple functions with `expect` and matchers like `toBe`, `toEqual`, etc.
- **Async/Await Testing**: Test promises and async/await patterns.
- **Mocking Fundamentals**: Mock functions, modules, and external API calls.
- **Code Coverage**: Configure Jest to generate coverage reports.
- **Test Suites**: Organize tests using `describe` blocks.
- **TDD Examples**: Implement functions using test-driven development.

## 📋 Prerequisites

- **Node.js** (v14+)
- **npm** (v6+) or **yarn**
- Basic knowledge of JavaScript (ES6+ syntax)

## 🛠 Installation

1. **Clone the repository**:
   bash
   git clone https://github.com/Abram-Emad/Jest-JS-Unit-Testing-Basic-Fundamentals-Testing.git
   cd Jest-JS-Unit-Testing-Basic-Fundamentals-Testing
   

2. **Install dependencies**:
   bash
   npm install
   # or
   yarn install
   

## 🧪 Running Tests

- **Run all tests**:
  bash
  npm test
  # or
  yarn test
  

- **Run tests in watch mode** (automatically re-runs on file changes):
  bash
  npm test -- --watch
  

- **Generate a code coverage report**:
  bash
  npm test -- --coverage
  
  The report will be available in the `coverage` directory.

---

## 📚 Examples

### 1. Testing a Simple Function
**Code**: `src/math.js`
javascript
const sum = (a, b) => a + b;
module.exports = { sum };


**Test**: `tests/math.test.js`
javascript
const { sum } = require('../src/math');

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});

test('adds negative numbers correctly', () => {
  expect(sum(-1, -2)).toBe(-3);
});


### 2. Testing Asynchronous Code
**Code**: `src/api.js`
javascript
const fetchData = async () => {
  // Simulates an API call
  return Promise.resolve('data');
};
module.exports = { fetchData };


**Test**: `tests/api.test.js`
javascript
const { fetchData } = require('../src/api');

test('fetches data successfully', async () => {
  const data = await fetchData();
  expect(data).toBe('data');
});


### 3. Mocking a Module
**Code**: `src/logger.js`
javascript
const logMessage = (message) => {
  console.log(message);
};
module.exports = { logMessage };


**Test**: `tests/logger.test.js`
javascript
jest.mock('../src/logger'); // Auto-mocks the module

const { logMessage } = require('../src/logger');

test('mocks the logging function', () => {
  logMessage('test');
  expect(logMessage).toHaveBeenCalledWith('test');
});


---

## 🧩 Test Structure

### Grouping Tests with `describe`
javascript
describe('Math Operations', () => {
  test('sum', () => { /* ... */ });
  test('subtract', () => { /* ... */ });
});


### Setup and Teardown
Use `beforeEach`, `afterEach`, `beforeAll`, and `afterAll` for repetitive tasks:
javascript
let database;

beforeEach(() => {
  database = initializeDatabase(); // Re-initialize before each test
});

afterAll(() => {
  closeDatabase(); // Cleanup after all tests
});


---

## 🤝 Contributing

Contributions are welcome! Follow these steps:
1. Fork the repository.
2. Create a branch: `git checkout -b feature/your-feature`.
3. Commit changes: `git commit -m 'Add some feature'`.
4. Push to the branch: `git push origin feature/your-feature`.
5. Open a pull request.

---

## 🙏 Acknowledgements

- [Jest Documentation](https://jestjs.io/docs/getting-started)
- Inspired by practical testing workflows in modern JavaScript development.
 

This README provides a thorough overview of the project, including setup instructions, usage examples, and testing best practices. Adjust paths or code snippets if they differ in the actual repository.
