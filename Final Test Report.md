# 🧪 Final Group Test Report — Word Puzzle Game Plus  
**Level:** Intermediate QA | **Week 5:** Test Management  
**Course:** Software Testing & Quality Assurance  
**Module:** Test Management (Week 5)  
**Project Type:** Group Assessment  
**Submission Date:** 2025-10-28  

---

## 👥 Team Information

| Role            | Name               | Responsibilities |
|-----------------|--------------------|------------------|
| Test Manager    | Asmamaw Yismaw     | Planning, scheduling, coordination, metric tracking |
| Risk Analyst    | Jostina Mwamburi   | Risk identification, prioritization, test design linkage |
| Test Executor   | Whitney Shisia     | Execution, evidence capture, defect logging |

&gt; ⚠️ Group rule confirmed: each member appears in **only one** submission.

---

## 🕹️ Project Overview

**System Under Test:** Word Puzzle Game Plus  
**Technology Stack:** HTML, CSS, Vanilla JavaScript  
**Environment:** Chrome 118 / Windows 11 (DevTools responsive mode tested)  
**Code Base:** https://github.com/PLP-Database-Design/wk-5-asmeyb-1/

### Features Under Test

| Feature      | Description                                      | Risk Category |
|--------------|--------------------------------------------------|---------------|
| Reset Game   | Clears score & progress instantly                | State integrity |
| Leaderboard  | Persists top-3 scores in localStorage            | Data boundary |
| Bonus Round  | Every 3 solved puzzles → score ×2                | Arithmetic / timing |

---

## 📋 Test Plan

### Objectives
- Validate functional correctness of new features  
- Achieve ≥ 80 % risk coverage  
- Keep defect density ≤ 0.3  
- All **high-priority** risks must have **≥ 1 test case**

### Scope
**In Scope:**  
- Reset logic, leaderboard CRUD, bonus arithmetic, input validation, UI feedback, localStorage edge cases  

**Out of Scope:**  
- Accessibility audit (planned next sprint), performance profiling, multiplayer features

### Tools & Resources
- **Test Board:** GitHub Projects (Kanban)  
- **Defects:** GitHub Issues with labels `severity:*` + `risk:*`  
- **Browser:** Google Chrome  
- **Snipping Tool:** Windows Sniping tool screenshots & screen recordings

### Schedule

| Phase            | Planned Duration | Actual Duration | Status   |
|------------------|------------------|-----------------|----------|
| Planning         | 2 h              | 2 h             | ✅       |
| Risk Analysis    | 3 h              | 3 h             | ✅       |
| Test Design      | 4 h              | 5 h             | ✅       |
| Execution        | 6 h              | 7 h             | ✅       |
| Regression       | 1 h              | 1 h             | ✅       |
| Report Assembly  | 2 h              | 2 h             | ✅       |

### Entry / Exit Criteria
- **Entry:** Code frozen in `main`, deployed to GitHub Pages, smoke test green  
- **Exit:** All high-priority test cases executed, zero critical defects, metrics approved by Test Manager

---

## Risk Analysis

### Risks

| ID | Feature | Risk Description | Likelihood | Impact | Priority | Mitigation Strategy |
|----|---------|------------------|------------|--------|----------|---------------------|
| R1|Reset Game |Reset button fails to clear score or puzzle progress correctly |high|high |high |Conduct repeated reset tests; verify counters reset to zero and game state reinitialized |
|R2|Leaderboard|Scores not stored or sorted correctly in localStorage|high|high|high|Test multiple scores|
|R3|Bonus Round|Bonus not triggered after every 3 puzzles|medium|medium|medium|Test sequences (3rd, 6th, 9th puzzles); confirm doubled score applied|
|R4|Hint system|Hint deduction (-2 points) misapplied or double-counted|medium|medium|medium|Verify hint deduction sequence and total score after use|
|R5|Scoring|Score overflow or negative value after repeated bonuses|low|low|low|Add boundary checks and validation for score value|
|R6|Responsive screen|Game layout not adapting correctly to various screen sizes|high|high|high|Apply responsive CSS grid/flexbox; test on multiple devices and breakpoints; use Chrome DevTools to simulate screens|
|R7|UI Buttons|Buttons freeze or overlap after rapid clicks|medium|medium|medium|Conduct rapid-click stress test; debounce actions|
|R8|Instructions / Rules|Player misinterprets hint cost or bonus rule|medum|medium|medium|Improve wording in Rules section; add in-game tooltip|
|R9|Puzzle variety|Game shows same or limited puzzles repeatedly instead of random new ones|high|high|high|Expand word database or randomize puzzle selection logic; test multiple sessions|

### Risk Coverage

- Tested Risks Percent: 90%
- Untested Risks Percent:10% 

## Test Cases

| ID | Feature | Objective | Expected Result | Actual Result | Status | Risk Link |
|----|---------|-----------|----------------|---------------|--------|-----------|
|T1|Reset Game |Verify reset clears score and progress |Resets to 0 | works as expected| passed|R1 |
|T2|Leaderboard|Validate descending sort (top 3 scores)|Sort correctly|works as expected|passed|R2|
|T3|Bonus Round|Verify ×2 score every 3rd puzzle|Bonus applied|work as expected|passes|R3|
|T4|Hint system|Verify hint deducts 2 points|Deduction works correctly|works as expected|passed|R4|
|T5|Scoring|Verify +10 points added for solving without hint|Each correct word adds +10|Points added correctly|passed|R5|
|T6|Responsive screen|Verify layout adjusts to different devices|Components resize and align properly|Layout breaks on small screens|failed|R6|
|T7|UI buttons|Test rapid clicks stability|No freeze/overlap|Minor lag|passed|R7|
|T8|Instruction|Evaluate clarity of rules|Player understands rules|slightly confusing|failed|R8|
|T9|Puzzle Variety|Verify new random puzzles appear after each solved one|Different words shown each round|Same few puzzles repeating|failed|R9|

## Defects

| ID | Issue Title                              | Severity | Risk ID | Status | GitHub Link          |
| -- | ---------------------------------------- | -------- | ------- | ------ | -------------------- |
|D1  |Responsive Layout Breaks on Medium Screen Sizes | High| R6     | Open   | [https://github.com/PLP-Database-Design/wk-5-asmeyb-1/issues/4] |
| D2 | Rules slightly confusing to players      | Medium   | R8      | Open   | [https://github.com/PLP-Database-Design/wk-5-asmeyb-1/issues/2]|
| D3 | Puzzle repetition — limited word variety | High     | R9      | Open   | [https://github.com/PLP-Database-Design/wk-5-asmeyb-1/issues/3]|


## Metrics

| Metric                      | Value | Formula / Basis                                      |
| --------------------------- | ----- | ---------------------------------------------------- |
| **Test Case Pass Percent**  | 66.7% | (6 passed / 9 total) × 100                           |
| **Defect Density**          | 0.33  | (3 defects / 9 test cases)                           |
| **Risk Coverage Percent**   | 90%   |                                                      |
| **Regression Success Rate** | 80%   | Based on re-testable features with minor issues only |
 

### Defect Summary

| Metric                   | Count              |
| ------------------------ | ------------------ |
| **Total Defects Logged** | 3                  |
| **Critical / High**      | 2                  |
| **Fix Rate**             | 0% (pending fixes) |


## Test Control & Project Management

### Phases

| **Phase**           | **Deliverable**             | **Actual Output**      | **Variance** | **Owner**     |
| ------------------- | --------------------------- | ---------------------- | ------------ | ------------- |
| **Planning**        | Test Plan Document          | Completed on schedule  | None         | Test Manager  |
| **Risk Analysis**   | Risk Assessment Report      | Completed successfully | None         | Risk Analyst  |
| **Test Design**     | Test Scenarios & Test Cases | Took 1 hour longer     | +1 hour      | Test Manager  |
| **Execution**       | Functional Test Report      | Executed as planned    | None         | Test Executor |
| **Regression**      | Retest after fixes          | Completed successfully | None         | Test Executor |
| **Report Assembly** | Final Test Summary Report   | Compiled and submitted | None         | Test Manager  |


**Progress Tracking Method:**  
**Change Control Notes:**

## Lessons Learned

- Most Defect Prone Feature: 
- Risk Analysis Impact: 
- Team Communication Effectiveness: 
- Improvements for Next Cycle: 

## Attachments

- 

## Sign Off

| Name | Role | Initials | Date |
|------|------|-----------|------|
| Asmamaw Yismaw | Test Manager | | |
| Jostina Mwamburi | Risk Analyst | | |
| Whitney Shisia | Test Executor | W.S| 10/26/2025|

## Overall Summary

**Statement:** 

**Test Status:** ☐ Completed / ☐ In Progress / ☐ Deferred
