# CSE325 Lab 1 - Testing 

This repo is for demoing the basics of testing using Node and Vitest.

## 1. Setup Instructions

Clone the repo locally:
Change `<Your username>` to your own username on Github

```bash
git clone git@github.com:ClarkCollege-CSE-SoftwareEngineering/lab-1-vitest-setup-<Your username>.git
```

Initialize a node project: 

```bash
npm init -y
```

Install Vitest and other dependencies:
```bash
npm install -D typescript vitest @vitest/coverage-v8
```

Run the tests:
```bash
npm run test
```

To see a full breakdown of test coverage, run coverage tests:
```bash
npm run test:coverage
```

## 2. Reflection Questions and Answers

### 2.3 Run the Tests

**Question:** Look at the add tests. The first test uses explicit Arrange-Act-Assert comments. Why might this pattern be useful, especially for complex tests?
**Answer:** Breaking down tests into the three parts of Arrange, Act, Assert makes it completely unambiguous which part of the test is doing what. It might be shorter to combine Arrange and Act into one line of code, but it becomes less clear that you are following proper testing principles. 

### 4.3 Understand the Difference

**Question:** The `strings.test.ts` file contains unit tests — they test individual functions in isolation. The `content.test.ts` file contains integration tests — they test how multiple units work together.
**Answer:** This is a correct statement. I'm not sure what other context is wanted here.

**Question:**