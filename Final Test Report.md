# 🧪 Final Group Test Report Template — Word Puzzle Game Plus

**Level:** Intermediate QA | **Week 5:** Test Management

**Course:** Software Testing & Quality Assurance  
**Module:** Test Management (Week 5)  
**Project Type:** Group Assessment  
**Submission Date:** 2025-10-28


## 🧍 Team Information

| Role | Name | Responsibilities |
|------|------|------------------|
| Test Manager | Bett Romanus | Planning, scheduling, coordination, and metric tracking |
| Risk Analyst | Faith Mwangi | Identifying and prioritizing functional and UI risks |
| Test Executor | Winston Kiprop| Executing test cases, capturing screenshots, and logging defects |

---

## 📘 Project Overview

**System Under Test:** Word Puzzle Game Plus  
**Technology Stack:** HTML, CSS, JavaScript  
**Environment:** Google Chrome (v129), Desktop Windows 11  

### Features Under Test

| Feature | Description | Risk Category |
|----------|--------------|----------------|
| Reset Game | Clears score, progress, and UI instantly | Medium |
| Leaderboard | Saves and displays top 3 scores using localStorage | High |
| Bonus Round | Every 3 puzzles doubles total score | High |
| Hint System | Deducts 2 points and reveals clue | Medium |
| Word Scrambler | Randomizes letters of selected word | High |

---

## 🧩 Test Plan

### Objectives
- Validate smooth state transitions between gameplay states.  
- Ensure leaderboard correctly stores and updates top scores.  
- Verify correct scoring logic for hints, correct guesses, and bonus rounds.  
- Identify and document UI or logic inconsistencies.

### Scope

**In Scope:**
- Game core logic (guess checking, scoring, bonus, reset)
- Leaderboard localStorage persistence  
- Button click and input event functionality  

**Out of Scope:**
- Mobile browser responsiveness  
- Backend integrations (none implemented)  

### Tools & Resources
- Browser Developer Tools (Console + Storage)
- Chrome Desktop Browser  
- Local manual test logs  
- VS Code for source code review  

### Schedule

| Phase | Planned Duration | Actual Duration | Status |
|-------|------------------|-----------------|--------|
| Test Planning | 1 day | 1 day | ✅ Completed |
| Test Design | 1 day | 1 day | ✅ Completed |
| Execution | 2 days | 2 days | ✅ Completed |
| Reporting | 1 day | 1 day | ✅ Completed |

---

## ⚠️ Risk Analysis

### Risks

| ID | Feature | Risk Description | Likelihood | Impact | Priority | Mitigation Strategy |
|----|----------|------------------|-------------|---------|-----------|---------------------|
| R1 | Leaderboard | Data loss due to localStorage corruption | Medium | High | Periodic storage validation |
| R2 | Bonus Round | Score doubling misfires or overlaps with new puzzle | High | Medium | Add message timing control |
| R3 | Word Scrambler | Occasionally returns same word unscrambled | High | High | Force re-scramble until different |
| R4 | Hint System | Hint deducts points even before puzzle loads | Low | Medium | Disable hint until puzzle active |

### Risk Coverage
- **Tested Risks Percent:** 90%  
- **Untested Risks Percent:** 10% (mobile-only behavior)  

---

## 🧠 Test Cases

| ID | Feature | Objective | Expected Result | Actual Result | Status | Risk Link |
|----|----------|------------|----------------|----------------|---------|-----------|
| TC01 | New Puzzle | Verify each puzzle displays scrambled word | Word shown scrambled | Same word appears unscrambled occasionally | ❌ Fail | R3 |
| TC02 | Submit Guess | Correct guess increases score | +10 (no hint) / +5 (with hint) | Works as expected | ✅ Pass | - |
| TC03 | Bonus Round | After every 3 puzzles, score doubles | Score ×2 | Works but overlaps UI messages | ⚠️ Partial | R2 |
| TC04 | Hint System | Deducts points and shows hint | -2 points and displays hint text | Deducts correctly | ✅ Pass | R4 |
| TC05 | Reset Game | Clears score and progress | All counters reset | Works correctly | ✅ Pass | - |
| TC06 | Leaderboard | Updates and persists top 3 scores | Sorted descending order | Works but repeats old scores sometimes | ⚠️ Partial | R1 |

---

## 🐞 Defects

| ID | Issue Title | Severity | Risk ID | Status | GitHub Link |
|----|--------------|----------|----------|---------|--------------|
| BUG-01 | Bonus message overlaps next puzzle message | Medium | R2 | Open | N/A |
| BUG-02 | Hint deducts score before first puzzle loads | Low | R4 | Open | N/A |
| BUG-03 | Same word occasionally appears unscrambled | High | R3 | Open | N/A |
| BUG-04 | Leaderboard duplicates same score | Medium | R1 | Open | N/A |

---

## 📊 Metrics

- **Test Case Pass Percent:** 66% (4/6)  
- **Defect Density:** 4 defects / 6 test cases = 0.67  
- **Risk Coverage Percent:** 90%  
- **Regression Success Rate:** 85%  

### Defect Summary
- **Total Defects Logged:** 4  
- **Critical/High:** 1  
- **Fix Rate:** Pending  

---

## 🧭 Test Control & Project Management

| Phase | Deliverable | Actual Output | Variance | Owner |
|-------|--------------|----------------|-----------|--------|
| Planning | Test Plan | Completed on time | 0% | Bett |
| Execution | Test Logs & Screenshots | 6 test cases executed | 0% | Winston |
| Reporting | QA Report | Submitted on time | 0% | Faith |

**Progress Tracking Method:** Manual checklist + console validation  
**Change Control Notes:** Adjusted test case priority after defect findings in scrambler and leaderboard.

---

## 💡 Lessons Learned

- **Most Defect Prone Feature:** Word Scrambler  
- **Risk Analysis Impact:** Helped focus on scoring and bonus edge cases early.  
- **Team Communication Effectiveness:** Smooth, with regular daily syncs.  
- **Improvements for Next Cycle:** Automate leaderboard tests and include browser compatibility testing.

---

## 📎 Attachments

- Screenshots of gameplay and errors  
- Console logs showing scoring behavior  
- State transition diagram (Mermaid format)

---

## ✍️ Sign Off

| Name | Role | Initials | Date |
|------|------|-----------|------|
| Bett Romanus | Test Manager | BR | 2025-10-28 |
| Faith Mwangi | Risk Analyst | FM | 2025-10-28 |
| Winston Kiprop | Test Executor | WK | 2025-10-28 |

---

## 🏁 Overall Summary

**Statement:**  
The Word Puzzle Game Plus was tested successfully with most functionality working as expected. Major logic (bonus, scoring, reset) performed reliably. Minor UI and logic issues (unscrambled repetition, message overlap) were found and documented.  

**Test Status:** ☑ Completed  