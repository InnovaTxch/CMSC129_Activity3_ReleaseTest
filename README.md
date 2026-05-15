# CMSC129 Activity 3 - Release Test Report

## a. Target App Summary
**Target App Name:** FINS (Finance Tracker)

FINS is an offline-first personal finance tracker that helps users record expenses, set budget limits, receive reminders, and view spending summaries and insights. The intended users are individuals who want a simple expense-tracking app without account setup. The app solves the problem of inconsistent daily financial tracking by giving users a local, always-available tool.

**Core Features (Top 5):**
1. Expense CRUD (create, read, update, delete)
2. Offline use with no login required
3. Budget and reminder notification settings
4. Receipt scan/upload with auto-filled fields
5. Summary reports and financial insights

## b. Requirements List (10 Requirements)
1. The app must run without internet connection.
2. The app must not require login before use.
3. The app must allow creating expense records.
4. The app must allow editing existing expense records.
5. The app must allow deleting expense records.
6. The app must support expense categories (preset and custom).
7. The app must support receipt scan or receipt image upload.
8. The app must allow budget limit configuration.
9. The app must allow reminder/notification configuration.
10. The app must show expense summaries and insights.

## c. Requirements-Based Testing

### REQUIREMENT #1
| Field | Value |
|---|---|
| Requirement | "The app must run without internet connection." |
| Test Input / Action | Disable internet connectivity, launch app, navigate dashboard and expenses page. |
| Expected Result | App remains usable and data is accessible offline. |
| Actual Result | App launched and core pages were usable offline. |
| Pass / Fail | ✅PASS |

### REQUIREMENT #2
| Field | Value |
|---|---|
| Requirement | "The app must not require login before use." |
| Test Input / Action | Launch app after install and attempt to proceed to core screens. |
| Expected Result | App opens without account credentials. |
| Actual Result | No login prompt; user can continue directly. |
| Pass / Fail | ✅PASS |

### REQUIREMENT #3
| Field | Value |
|---|---|
| Requirement | "The app must allow creating expense records." |
| Test Input / Action | Open add expense screen, enter amount/date/category, then save. |
| Expected Result | New expense appears in expense list. |
| Actual Result | New expense was successfully added. |
| Pass / Fail | ✅PASS |

### REQUIREMENT #4
| Field | Value |
|---|---|
| Requirement | "The app must allow editing existing expense records." |
| Test Input / Action | Select existing expense, modify amount/category/date, save updates. |
| Expected Result | Updated values are shown in list/detail. |
| Actual Result | Record updates were reflected correctly. |
| Pass / Fail | ✅PASS |

### REQUIREMENT #5
| Field | Value |
|---|---|
| Requirement | "The app must allow deleting expense records." |
| Test Input / Action | Select expense entry, trigger delete action, confirm deletion. |
| Expected Result | Expense is removed from records. |
| Actual Result | Entry was removed and no longer visible. |
| Pass / Fail | ✅PASS |
| Remark | Feature works, but with caveats. The delete interaction is not clearly communicated (swipe-to-delete with undo), and deletion is only finalized after the snackbar timeout ends, which can feel delayed. |

### REQUIREMENT #6
| Field | Value |
|---|---|
| Requirement | "The app must support expense categories (preset and custom)." |
| Test Input / Action | Add one expense with preset category and one with custom category. |
| Expected Result | Both entries save with selected categories. |
| Actual Result | Preset and custom categories both worked. |
| Pass / Fail | ✅PASS |

### REQUIREMENT #7
| Field | Value                                                                                       |
|---|---------------------------------------------------------------------------------------------|
| Requirement | "The app must support receipt scan or receipt image upload."                                |
| Test Input / Action | Open receipt feature, run camera scan or upload a receipt image, review auto-filled fields. |
| Expected Result | Relevant fields are auto-filled and editable.                                               |
| Actual Result | Input fields were either inaccurately filled or left empty.                                 |
| Pass / Fail | ❌ FAIL                                                                                      |

### REQUIREMENT #8
| Field | Value                                                                            |
|---|----------------------------------------------------------------------------------|
| Requirement | "The app must allow budget limit configuration."                                 |
| Test Input / Action | Open Customizations page, set budget value, save, and reopen customization page. |
| Expected Result | Budget value persists after save.                                                |
| Actual Result | Budget settings were saved successfully.                                         |
| Pass / Fail | ✅PASS                                                                            |

### REQUIREMENT #9
| Field | Value |
|---|---|
| Requirement | "The app must allow reminder/notification configuration." |
| Test Input / Action | Open notification settings, set reminder time/frequency, save settings. |
| Expected Result | Notification setting persists and schedules reminder. |
| Actual Result | Reminder settings were saved. |
| Pass / Fail |  ✅PASS |

### REQUIREMENT #10
| Field | Value |
|---|---|
| Requirement | "The app must show expense summaries and insights." |
| Test Input / Action | Add multiple expenses across dates, open summary and insights pages. |
| Expected Result | Summary totals/comparisons and advice are displayed. |
| Actual Result | Summary and insight views generated expected outputs. |
| Pass / Fail | ✅PASS |

## d. Scenario-Based Testing

### Scenario 1: Daily Expense Tracking
**User Story:** As a student, I want to log daily expenses quickly so that I can monitor spending habits.

| Step | Action | Expected Behavior | Result | Remarks (if fail) |
|---|---|---|---|---|
| 1 | Open the app | Dashboard/home screen loads successfully. | ✅PASS | N/A |
| 2 | Go to add expense page and input breakfast expense | Expense form accepts input. | ✅PASS | N/A |
| 3 | Add commute and school supply expenses | New entries appear in expense list. | ✅PASS | N/A |
| 4 | Open summary/dashboard view | Totals update based on newly added entries. | ✅PASS | N/A |

### Scenario 2: Monthly Budget Management
**User Story:** As a budget-conscious user, I want to set a monthly budget and get reminders so that I stay within limits.

| Step | Action | Expected Behavior | Result | Remarks (if fail) |
|---|---|---|---|---|
| 1 | Open settings and set monthly budget | Budget value is accepted and saved. | ✅PASS | N/A |
| 2 | Configure reminder notification schedule | Reminder preferences are saved. | ✅PASS | N/A |
| 3 | Add expenses across multiple days | Expenses are recorded properly. | ✅PASS | N/A |
| 4 | Open summary/insights | Spending progress is reflected in reports/insights. | ✅PASS | N/A |

## e. Summary
### i. Testing Summary
All 10 listed requirements were tested through black-box validation, and 9 out of 10 tests passed under the test run used for this release test. Two user scenarios were executed and passed, confirming expected behavior in routine use.

### ii. Conclusion
The app is **ready for release testing use** in its current scope. Core workflows (expense CRUD, offline usage, categories, budget/reminders, summaries/insights) are functional and consistent with documented requirements.

### iii. Remarks
- Major strength: offline-first usability with no login barrier.
- Urgent fix: improve the receipt scanner’s accuracy in detecting and extracting expense data from images.
- UX caution: destructive actions (delete/edit) should always include confirmation popups to prevent accidental data loss.
- Future improvement:
    - implement proper soft delete mechanism.
    - add built-in export/backup options to reduce local-only data risk.
    - add responsive effects to pressable elements to provide users with haptic feedback when changes occur.