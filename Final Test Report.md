# 🧪 Final Group Test Report — Word Puzzle Game Plus

**Level:** Intermediate QA | **Week 5:** Test Management
**Course:** Software Testing & Quality Assurance
**Module:** Test Management (Week 5)
**Project Type:** Group Assessment
**Submission Date:** 2025-10-28

---

## 👥 Team Information

| Role          | Name         | Responsibilities                                         |
| ------------- | ------------ | -------------------------------------------------------- |
| Test Manager  | Bett Romanus | Planning, scheduling, coordination, metric tracking      |
| Risk Analyst  | Faith Mwangi | Risk identification, prioritization, test design linkage |
| Test Executor | Winston Kiprop | Execution, evidence capture, defect logging              |

---

## 📜 Group Rules

* Each student must belong to only one group.
* Duplicate membership or multiple submissions will result in invalidation.
* Every group member must contribute towards this project.

---

## 💡 Project Overview

**System Under Test:** Word Puzzle Game Plus
**Technology Stack:** HTML, CSS, JavaScript
**Environment:** Chrome Browser (Desktop, Version 129+)

### Features Under Test

| Feature     | Description                         | Risk Category |
| ----------- | ----------------------------------- | ------------- |
| Reset Game  | Clears score and progress instantly | Medium        |
| Leaderboard | Stores top 3 scores in localStorage | High          |
| Bonus Round | Every 3 puzzles → doubles score     | High          |

---

## 🧩 1️⃣ Test Plan

### Objectives

* Verify the correctness of word puzzle logic, scoring, and bonus rounds.
* Validate leaderboard functionality (sorting, saving, and displaying top scores).
* Ensure “Reset” restores the game to default state without residual data.

### Scope

**In Scope:**

* UI interaction testing (buttons, input fields).
* Functional testing of leaderboard, bonus logic, and reset.
* Risk-based and regression testing on the main gameplay loop.

**Out of Scope:**

* Mobile browser optimization.
* Sound effects or advanced UI animations.

### Resources

**Roles:** Defined in Team Information above.
**Tools Used:**

* Chrome DevTools
* GitHub Issues (for defect tracking)
* Google Sheets (test case management)
* Snipping Tool (for screenshots)

### Schedule

| Phase       | Planned Duration | Actual Duration | Status      |
| ----------- | ---------------- | --------------- | ----------- |
| Planning    | 1 day            | 1 day           | ✅ Completed |
| Test Design | 1 day            | 1 day           | ✅ Completed |
| Execution   | 2 days           | 2 days          | ✅ Completed |
| Reporting   | 1 day            | 1 day           | ✅ Completed |

### Entry Criteria

* Game build deployed on localhost.
* Feature list verified and stable.

### Exit Criteria

* 100% test case execution.
* All critical defects closed or deferred with justification.

### Environment

* **Browser:** Chrome (Desktop)
* **OS:** Windows 11 / macOS Sonoma
* **Display Resolution:** 1366×768 or higher

---

## ⚠️ 2️⃣ Risk Analysis

### Identified Risks

| ID | Feature     | Risk Description                    | Likelihood | Impact | Priority | Mitigation Strategy              |
| -- | ----------- | ----------------------------------- | ---------- | ------ | -------- | -------------------------------- |
| R1 | Leaderboard | Scores not sorted properly          | High       | High   | High     | Validate descending order logic  |
| R2 | Leaderboard | LocalStorage not persisting data    | Medium     | High   | High     | Test persistence after reload    |
| R3 | Bonus Round | Bonus not triggered after 3 puzzles | High       | Medium | High     | Add counter validation           |
| R4 | Reset       | Reset not clearing all progress     | Medium     | Medium | Medium   | Test multiple consecutive resets |
| R5 | UI          | Buttons overlap or text misaligned  | Low        | Medium | Low      | Usability & layout checks        |
| R6 | Performance | Game lag on multiple resets         | Low        | High   | Medium   | Observe FPS and reload frequency |

### Risk Coverage

* **Tested Risks Percent:** 83%
* **Untested Risks Percent:** 17%

🟢 **High Risks:** R1, R2, R3
🟠 **Medium Risks:** R4, R6
🟡 **Low Risks:** R5

---

## 🧠 3️⃣ Test Design & Execution

### Test Cases

| ID    | Feature          | Objective                              | Steps                          | Expected Result           | Actual Result     | Status         | Risk Link |
| ----- | ---------------- | -------------------------------------- | ------------------------------ | ------------------------- | ----------------- | -------------- | --------- |
| TC-01 | Reset            | Verify reset clears game progress      | Start game → Press Reset       | All fields cleared        | Works as expected | ✅ Pass         | R4        |
| TC-02 | Leaderboard      | Verify scores are sorted descending    | Play 3 games (scores 5, 12, 8) | Order: 12, 8, 5           | Order correct     | ✅ Pass         | R1        |
| TC-03 | Leaderboard      | Validate persistence on reload         | Achieve score → Reload page    | Score retained            | Works correctly   | ✅ Pass         | R2        |
| TC-04 | Bonus Round      | Verify bonus activates every 3 puzzles | Complete 3 puzzles             | Bonus score doubled       | Works correctly   | ✅ Pass         | R3        |
| TC-05 | Input Validation | Check behavior for blank input         | Submit empty field             | Error shown or ignored    | Error displayed   | ✅ Pass         | R5        |
| TC-06 | Reset            | Stress test multiple resets            | Rapidly reset 5×               | No lag or freeze          | Minor delay       | ⚠️ Minor issue | R6        |
| TC-07 | UI Usability     | Check alignment and button visibility  | Observe layout                 | Buttons aligned correctly | Fine              | ✅ Pass         | R5        |
| TC-08 | Negative         | Enter invalid characters in puzzle     | Type special chars             | Error or ignored input    | Error handled     | ✅ Pass         | R5        |

---

## 🪲 4️⃣ Defect Reporting

| ID | Issue Title                                     | Severity | Risk ID | Status | GitHub Link                                                |
| -- | ----------------------------------------------- | -------- | ------- | ------ | ---------------------------------------------------------- |
| D1 | Reset button occasionally misses clearing score | Medium   | R4      | Open   | [#1](https://github.com/PLP-Database-Design/wk-5-RomanusBett-1/issues/2) |
| D2 | Bonus not triggered if puzzle skipped           | High     | R3      | Open | [#2](https://github.com/PLP-Database-Design/wk-5-RomanusBett-1/issues/3) |
| D3 | Slight lag on repeated reset                    | Low      | R6      | Open   | [#3](https://github.com/PLP-Database-Design/wk-5-RomanusBett-1/issues/4) |

---

## 📊 5️⃣ Test Monitoring & Metrics

| Metric                  | Description            | Result    |
| ----------------------- | ---------------------- | --------- |
| Test Case Pass %        | (7 / 8) × 100          | **87.5%** |
| Defect Density          | (3 defects / 8 cases)  | **0.38**  |
| Risk Coverage           | (5 / 6) × 100          | **83%**   |
| Regression Success Rate | (4 / 5 retests passed) | **80%**   |

### Charts Summary

🟢 Passed — 87.5%
🔴 Failed — 12.5%
🟠 High Risk Coverage — 83%

---

## 🧭 6️⃣ Test Control & Project Management

| Phase     | Deliverable  | Actual Output | Variance | Owner |
| --------- | ------------ | ------------- | -------- | ----- |
| Planning  | Test Plan    | Delivered     | 0%       | Bett  |
| Design    | Test Cases   | Delivered     | 0%       | Faith  |
| Execution | Test Results | Delivered     | 0%       | Winston |
| Reporting | Final Report | Delivered     | 0%       | All   |

**Progress Tracking Method:** Google Sheets & Daily check-ins
**Change Control Notes:** Adjusted scope to exclude mobile after Day 2 testing.

---

## 💬 Reflection

### Lessons Learned

* **Most Defect-Prone Feature:** Reset button behavior.
* **Risk Analysis Impact:** Prioritized leaderboard and bonus logic tests, catching two critical bugs early.
* **Collaboration Effectiveness:** Daily syncs improved defect turnaround.
* **Improvements for Next Cycle:** Automate leaderboard tests using Cypress for better regression accuracy.

---

## 📎 Attachments

* Test evidence screenshots
* GitHub Issues export
* Excel sheet for metrics tracking

---

## ✅ Sign Off

| Name         | Role          | Initials | Date       |
| ------------ | ------------- | -------- | ---------- |
| Bett Romanus | Test Manager  | BR       | 2025-10-28 |
| Faith Mwangi | Risk Analyst  | FM       | 2025-10-28 |
| Winston Kiprop | Test Executor | WK       | 2025-10-28 |

---

## 🏁 Overall Summary

**Statement:**
All core features of *Word Puzzle Game Plus* were successfully tested. Risk-based prioritization ensured that critical gameplay functions were validated thoroughly. Remaining minor defects have been logged for future release cycles.

**Test Status:** ✅ Completed
