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

**Question:** If the slugify function had a bug, which tests would fail? 

**Answer:** Both the unit tests in strings.test.ts AND the integration tests in content.test.ts

**Question:** What additional confidence do the integration tests give you that unit tests alone wouldn't provide?

**Answer:** Integration tests give you the confidence that multiple parts are working together correctly. A passing unit test might still result in a project bug if individual functions/classes do not interact with each other correctly. 

## 3. Additional Tests

Four additional tests are listed below, underneath their respective functions

`strings.slugify()`

```typescript
    it('handles an empty string', () => {
      expect(slugify('')).toBe('');
    });
```

`strings.truncate()`
```typescript
    it('returns empty string for max length of 0', () => {
      expect(truncate('Hello', 0, '')).toBe('');
    });
```

`strings.capitalize()`
```typescript
    it('handles input that is already correctly capitalized', () => {
      expect(capitalize('Hello')).toBe('Hello');
    });
```

`strings.countWords()`
```typescript
    it('counts hyphenated words as one word', () => {
      expect(countWords('I need to double-check the booby-trapped ice-skate rink tomorrow')).toBe(9);
    });
```

## 4. Testing Trophy Connection

Starting with the bottom layer of the Trophy Model, the `tsconfig.json` has strict type checking for checking type errors in the code. Alongside with syntax highlighting in VScode, these all form the foundation for syntax and type checking in the static layer or base of the trophy. Unit tests is a small, yet it is the next foundational part of the trophy. Writing clear and concise unit tests allows you to spend more time and effort in the next layer which is the most important and largest section of the trophy model: Integration tests. Integration testing is the most important layer of the model as it test interactive funcitonality across the entire project, and provides a great balance between confidence and time/resources spent. End-to-end tests is the final part of the trophy model, and could be represented in this lab by the Github Actions which can repeatedly test the same things a user might interact with. 

### Contributors
Patrick Neill - CSE325: Software Design & Development