# Contribution 1: Add compatibility test for $tsIncrement (second pass)

**Contribution Number:** 1  
**Student:** Ryan Garfinkel  
**Issue:** [https://github.com/documentdb/functional-tests/issues/210](https://github.com/documentdb/functional-tests/issues/210)  
**Status:** Phase II Complete

---

## Why I Chose This Issue

I chose this issue because it aligns with my intrest in ensuring some reliability with components in code. This helps ground sytsem behavior and can indicate any regression as new bug fixes or features are added. While the $tsIncrement operator seems simple, writing test cases will push me to think about edge cases and what it means to use this operator. I'm hoping to get a better understanding of test driven development working with new testing frameworks and mocking data to simulate parts of runtime.

---

## Understanding the Issue

### Problem Description

There is currently only one test that covers the $tsIncrement operator, which tests for basic functionality. There are no tests for edge cases.

### Expected Behavior

There should be more tests for the $tsIncrement operator that extensively cover its behavior and its handeling of edge cases, type errors, and null values.

### Current Behavior

At the moment, the one smoke test runs and passes as expected.

### Affected Components

The only affected operator is the $tsIncrement operator. Resolving this issue will invole adding more tests to in the documentdb_tests/compatibility/tests/core/operator/expressions/timestamp/tsIncrement directory. 

---

## Reproduction Process

### Environment Setup

I initally needed to setup an environment to install all required packages. I created the environment using python venv using python 3.11.1.

### Steps to Reproduce

1. Create virtual environment with `python3 -m venv .venv`
2. Activate environment with `source .venv/bin/activate` (different command on windows)
3. Install python requirements with `pip install -r requirements.txt`
4. Run existing $tsIncrement operator tests with `python -m pytest documentdb_tests/compatibility/tests/core/operator/expressions/timestamp/tsIncrement/ --collect-only`

### Reproduction Evidence

- **Commit showing reproduction:** [Link to the branch on my fork](https://github.com/RyanGarfinkel/functional-tests/tree/add-tsIncrement-compatibility-tests)
- **Screenshots/logs:** [If applicable]
- **My findings:** I found that there was only one smoke test covering the $tsIncrement operator that tests basic functionality.

---

## Solution Approach

### Analysis

[Your analysis of the root cause - what's causing the issue?]

### Proposed Solution

[High-level description of your fix approach]

### Implementation Plan

Using UMPIRE framework (adapted):

**Understand:** The $tsIncrement operator currently has one test that covers basic funcationity with only one timestamp. It needs additional tests to cover more complex functionality and possible errors like missing vales or invalid data types.

**Match:** There are similar expression related tests that are similar to the $tsIncrement operator, and other tests check for null/missing values and invalid data types.

**Plan:** [Step-by-step implementation plan]
1. Create a tsIncrement base class in the utils folder.
2. Create tests for null values.
3. Create tests for invalud data types.
4. Add additional tests in expressions that utilize the tsIncrement operator.

**Implement:** [Link to the branch on my fork](https://github.com/RyanGarfinkel/functional-tests/tree/add-tsIncrement-compatibility-tests)

**Review:** 
- [ ] All tests have docstrings to convey their purpose.
- [ ] Any constants are imported from test_constants.py.
- [ ] Each test makes only one assertion.
- [ ] Any shared dataclasses live in `utils/` directory.
- [ ] Any new filenames follow the test_tsIncrement_{feature}.py name style.

**Evaluate:** In addition to there being a complete suite of tests that pass, the additional compatability tests can run on a live MongoDB database.

---

## Testing Strategy

### Unit Tests

- [ ] Test case 1: [Description]
- [ ] Test case 2: [Description]
- [ ] Test case 3: [Description]

### Integration Tests

- [ ] Integration scenario 1
- [ ] Integration scenario 2

### Manual Testing

[What you tested manually and results]

---

## Implementation Notes

### Week [X] Progress

[What you built this week, challenges faced, decisions made]

### Week [Y] Progress

[Continue documenting as you work]

### Code Changes

- **Files modified:** [List]
- **Key commits:** [Links to important commits]
- **Approach decisions:** [Why you chose certain approaches]

---

## Pull Request

**PR Link:** [GitHub PR URL when submitted]

**PR Description:** [Draft or final PR description - much of the content above can be adapted]

**Maintainer Feedback:**
- [Date]: [Summary of feedback received]
- [Date]: [How you addressed it]

**Status:** [Awaiting review / Iterating / Approved / Merged]

---

## Learnings & Reflections

### Technical Skills Gained

[What you learned technically]

### Challenges Overcome

[What was hard and how you solved it]

### What I'd Do Differently Next Time

[Reflection on your process]

---

## Resources Used

- [Link to helpful documentation]
- [Tutorial or Stack Overflow post that helped]
- [GitHub issues or discussions that helped]
