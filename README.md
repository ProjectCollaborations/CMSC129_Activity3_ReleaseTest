# PondStat

PondStat is a comprehensive mobile application built with Flutter, designed to help aquaculture farmers and students efficiently manage and monitor their ponds. Whether farming Shrimp or Tilapia, PondStat provides tools for tracking pond growth, monitoring water quality parameters, managing daily feed consumption and expenses, supporting offline data entry, and analyzing pond performance.

The app is designed to help aquaculture students, specifically F125 students, transition from managing data in multiple Excel sheets to a unified and efficient digital platform. It solves problems such as scattered records, data loss, difficulty in historical analysis, and delayed response to critical pond conditions.

---

# Core Features

## 1. Authentication

- Secure Google Sign-In
- Restricted access for authorized accounts
- Whitelisted reviewer account support
- User account access managed through Firebase Authentication

---

## 2. Dashboard Overview

- Displays active ponds
- Shows current culture periods
- Provides key pond statistics
- Gives users a high-level view of pond status and performance

---

## 3. Pond Management

- Create new pond records
- Edit existing pond details
- Delete pond records
- Cascading deletion of associated pond data such as measurements, feed logs, and finances

---

## 4. Water Quality Monitoring

- Log pH values
- Log dissolved oxygen values
- Log temperature values
- Log salinity values
- Display saved water quality records under the selected pond

---

## 5. Visual Alerts

- Detect water quality values outside acceptable ranges
- Display warning indicators or notifications
- Help users respond quickly to abnormal pond conditions

---

## 6. Biometric Growth Tracking

- Record biometric sampling data
- Store sample count, average weight, and other available biometric measurements
- Display biometric records under the selected pond

---

## 7. Growth Visualization and Biomass Estimation

- Visualize growth curves based on recorded biometric data
- Provide biomass estimates over time
- Support analysis of pond growth performance

---

## 8. Feed and Expense Tracking

- Record daily feed consumption
- Record related expenses
- Calculate or display Feed Conversion Ratio (FCR)
- Support financial and operational monitoring

---

## 9. Offline Support

- Display offline status when there is no internet connection
- Keep previously loaded data visible while offline
- Support automatic syncing when internet connection is restored
- Intended to allow pond-edge data entry in areas with unstable connectivity

---

## 10. Role-Based Access Control

- Distinguish between Farm Owner and Technician permission levels
- Restrict Technician access to Farm Owner-only actions
- Display permission-denied messages for unauthorized actions

---

# Requirements-Based Testing

## Requirement #1

| Field | Description |
|---|---|
| **Requirement** | The app shall authenticate users securely via Google Sign-In, restricted to authorized accounts. |
| **Test Input/Action** | Opened the app and attempted to sign in using the whitelisted Google reviewer account. |
| **Expected Result** | The authorized account should successfully log in and access the app. Unauthorized accounts should be denied access and should not be redirected to the dashboard. |
| **Actual Result** | The app authenticated the user securely via Google Sign-In. The tester successfully logged in and accessed the app. |
| **Pass/Fail** | ✅ Pass |

---

## Requirement #2

| Field | Description |
|---|---|
| **Requirement** | The app shall display a dashboard providing a high-level overview of all active ponds, current culture periods, and key statistics. |
| **Test Input/Action** | Logged in to the app and navigated to the Dashboard. Observed the pond cards, active ponds, culture period details, and displayed statistics. |
| **Expected Result** | The dashboard should load successfully and display all active ponds, their current culture periods, and key statistics such as species, stocking date, age of culture, or other available summary data. |
| **Actual Result** | The dashboard loaded successfully and displayed all active ponds, their current culture periods, and key statistics such as species, stocking date, age of culture, and other available summary data. |
| **Pass/Fail** | ✅ Pass |

---

## Requirement #3

| Field | Description |
|---|---|
| **Requirement** | The app shall allow users to create, edit, and delete ponds, with deletion triggering a cascading removal of all associated data, including measurements, feed logs, and finances. |
| **Test Input/Action** | Created a test pond, edited its details, added sample measurements, feed logs, and finance records, then deleted the pond. Checked whether the pond and all associated records were removed. |
| **Expected Result** | The user should be able to create and edit pond records. When the pond is deleted, it should be removed from the dashboard and all related measurements, feed logs, and finance records should also be removed. |
| **Actual Result** | The user was able to create and edit pond records. When the pond was deleted, it was removed from the dashboard together with its related measurements, feed logs, and finance records. However, the edit/delete function was not easy to find because it was hidden and there were no clear instructions. |
| **Pass/Fail** | ✅ Pass |

---

## Requirement #4

| Field | Description |
|---|---|
| **Requirement** | The app shall allow users to log water quality parameters such as pH, dissolved oxygen, temperature, and salinity. |
| **Test Input/Action** | Opened an existing pond, navigated to the Water Quality section, entered valid values for pH, dissolved oxygen, temperature, and salinity, then saved the entry. |
| **Expected Result** | The water quality entry should be saved successfully and displayed under the selected pond's monitoring records. |
| **Actual Result** | The water quality entry was saved successfully and displayed under the selected pond's monitoring records. However, there was an issue with the database because some custom-made parameter names such as "d", "dd", and "fef" were still visible even though the account was newly created. |
| **Pass/Fail** | ✅ Pass |

---

## Requirement #5

| Field | Description |
|---|---|
| **Requirement** | The app shall display visual alerts when water quality parameter values fall outside acceptable ranges. |
| **Test Input/Action** | Opened the Water Quality section and entered an abnormal water quality value, such as critically low dissolved oxygen or an out-of-range pH value. Saved the entry and observed the displayed record. |
| **Expected Result** | The app should display a clear visual alert, warning indicator, color change, or warning message showing that the entered value is outside the acceptable range. |
| **Actual Result** | The app displayed a clear visual alert, warning indicator, or message when the entered value was outside the acceptable range. The app notified the user when the value was out of range. |
| **Pass/Fail** | ✅ Pass |

---

## Requirement #6

| Field | Description |
|---|---|
| **Requirement** | The app shall allow users to record biometric sampling data. |
| **Test Input/Action** | Opened the Biometric Growth section of a pond and entered biometric sampling data such as sample count, average weight, or other available measurement fields. Saved the entry. |
| **Expected Result** | The biometric sampling data should be saved successfully and displayed under the selected pond's biometric records. |
| **Actual Result** | The biometric sampling data was saved successfully and displayed under the selected pond's biometric records. |
| **Pass/Fail** | ✅ Pass |

---

## Requirement #7

| Field | Description |
|---|---|
| **Requirement** | The app shall visualize growth curves and provide biomass estimates over time based on biometric data. |
| **Test Input/Action** | Added at least two biometric sampling records on different dates, then opened the growth visualization or analytics section. |
| **Expected Result** | The app should display a growth curve based on the recorded biometric data and provide a biomass estimate over time. |
| **Actual Result** | The app displayed a growth curve based on the recorded biometric data and provided a biomass estimate over time. |
| **Pass/Fail** | ✅ Pass |

---

## Requirement #8

| Field | Description |
|---|---|
| **Requirement** | The app shall allow users to track daily feed consumption and related expenses, and calculate Feed Conversion Ratio (FCR). |
| **Test Input/Action** | Opened the Feed, Operations, or Finances section. Entered a daily feed consumption record and related expense, then checked whether the app displayed or calculated the Feed Conversion Ratio. |
| **Expected Result** | The feed consumption and expense records should be saved successfully. The app should display or calculate the Feed Conversion Ratio based on the available feed and growth data. |
| **Actual Result** | The feed consumption and expense records were saved successfully. The app displayed or calculated the Feed Conversion Ratio based on the available feed and growth data. However, when offline, the save button only kept loading until an internet connection was restored. |
| **Pass/Fail** | ✅ Pass |

---

## Requirement #9

| Field | Description |
|---|---|
| **Requirement** | The app shall support offline data entry by caching operations locally and automatically syncing pending data to the cloud upon reconnection. |
| **Test Input/Action** | Enabled airplane mode or disconnected the device from the internet. Added a new monitoring or feed record while offline. Reconnected to the internet and observed whether the data synced automatically. |
| **Expected Result** | The app should show an offline indicator or banner. The entry should be saved locally while offline. Once internet connection returns, the pending data should automatically sync to the cloud without requiring manual action. |
| **Actual Result** | The app showed an offline indicator or banner, and previously saved data remained visible. However, during scenario testing, a new feed entry could not be saved while offline because the save action kept loading until internet connection was restored. |
| **Pass/Fail** | ❌ Fail |

---

## Requirement #10

| Field | Description |
|---|---|
| **Requirement** | The app shall enforce role-based access control by distinguishing between Farm Owner and Technician permission levels. |
| **Test Input/Action** | Logged in using a Technician account and attempted to perform a Farm Owner-only action, such as deleting a pond or modifying restricted farm-level settings. |
| **Expected Result** | The app should prevent the Technician from performing restricted actions and display a clear permission-denied message. |
| **Actual Result** | The app prevented the Technician from performing restricted actions and displayed a permission-denied message. However, the app did not visibly show the user role. The role only appeared in the profile area through the "add collaborators" tab when the user had only one pond. Adding another pond removed the "add collaborators" tab. |
| **Pass/Fail** | ✅ Pass |

---

# Scenario-Based Testing

# User Scenario #1: Student Monitoring a Pond and Responding to a Water Quality Alert

**User Story:**  
As a Student, I want to monitor my pond's water quality and be alerted to dangerous readings, so that I can act quickly and prevent possible stock loss.

| Step | Action | Expected Behavior | Result | Remarks |
|---|---|---|---|---|
| 1 | Open the app and log in using the Farm Owner account | Dashboard loads and shows all active ponds | ✅ Pass | |
| 2 | Tap on an active pond to open its details | Pond detail view opens successfully with monitoring sections | ✅ Pass | |
| 3 | Navigate to the Water Quality section | Water Quality section loads with previous parameter entries and an option to add a new entry | ✅ Pass | |
| 4 | Tap "Add Entry" and input a dissolved oxygen value of 2.0 mg/L | The input form accepts the value | ✅ Pass | |
| 5 | Save the parameter entry | The entry is saved successfully | ✅ Pass | |
| 6 | Observe the saved dissolved oxygen value | The DO value is flagged with a visual alert indicating that it is below the safe threshold | ✅ Pass | |
| 7 | Navigate back to the Dashboard | Dashboard still reflects the active pond and no data loss is observed | ✅ Pass | |

---

# User Scenario #2: Technician Logging Feed Data While Offline

**User Story:**  
As a Technician at the pond edge, I want to log daily feed consumption even without internet access, so that no data is lost due to connectivity issues in the field.

| Step | Action | Expected Behavior | Result | Remarks |
|---|---|---|---|---|
| 1 | Open the app and log in using the Technician account while connected to the internet | The user is authenticated and redirected to the dashboard | ✅ Pass | |
| 2 | Enable airplane mode on the device | Network connection is disabled and the app displays an offline status banner | ✅ Pass | |
| 3 | Open an existing pond record | Previously loaded or cached pond data remains accessible | ✅ Pass | |
| 4 | Navigate to the Feed, Operations, or Finances section | The section opens and allows the user to input feed-related data | ✅ Pass | |
| 5 | Tap "Add Feed Entry" and input 5 kg of feed with a cost of ₱250 | The form accepts the values while offline | ❌ Fail | The form accepted values offline, but the entry could not be saved. |
| 6 | Save the feed entry | The entry is saved locally and a confirmation is shown despite being offline | ❌ Fail | The entry was not saved locally while offline. |
| 7 | Disable airplane mode to restore connectivity | The app detects reconnection and automatically syncs the pending entry to Firestore | ✅ Pass | |
| 8 | Refresh or reopen the pond record | The newly added feed entry remains visible after syncing | ✅ Pass | |

---

# Summary

## Testing Summary

The application underwent both requirements-based testing and scenario-based testing to validate its core functionalities and user experience.

Most required features were successfully implemented and passed testing, including:

- Secure Google Sign-In authentication
- Dashboard overview of active ponds and key statistics
- Pond creation, editing, and deletion
- Cascading deletion of associated pond data
- Water quality parameter logging
- Visual alerts for abnormal water quality values
- Biometric sampling data recording
- Growth curve visualization
- Biomass estimation
- Feed consumption and expense tracking
- Feed Conversion Ratio calculation
- Role-based access control

Out of the ten listed requirements, nine passed while one failed. The failed requirement involved offline data entry and syncing because a new feed entry could not be saved locally while the device was offline. Although the app displayed an offline banner and previously saved data remained visible, the expected offline write operation did not fully work as required.

Scenario-based testing also showed that the application performs well in realistic user interactions. The Farm Owner scenario passed all steps, confirming that the app supports pond monitoring and water quality alert workflows. However, the Technician offline feed logging scenario had failed steps because the app accepted the feed entry input but could not save the entry while offline.

---

## Requirements-Based Testing Result

| Requirement No. | Requirement Summary | Result |
|---|---|---|
| 1 | Google Sign-In authentication restricted to authorized accounts | ✅ Pass |
| 2 | Dashboard overview of active ponds, culture periods, and key statistics | ✅ Pass |
| 3 | Create, edit, and delete ponds with cascading deletion | ✅ Pass |
| 4 | Log water quality parameters | ✅ Pass |
| 5 | Display visual alerts for abnormal water quality values | ✅ Pass |
| 6 | Record biometric sampling data | ✅ Pass |
| 7 | Visualize growth curves and biomass estimates | ✅ Pass |
| 8 | Track feed consumption, expenses, and FCR | ✅ Pass |
| 9 | Offline data entry and automatic cloud syncing | ❌ Fail |
| 10 | Role-based access control | ✅ Pass |

---

## Scenario-Based Testing Result

| Scenario No. | Scenario Summary | Result |
|---|---|---|
| 1 | Farm Owner monitors water quality and responds to alert | ✅ Pass |
| 2 | Technician records feed data while offline | ❌ Fail |

---

## Conclusion

The application is mostly ready for release since the majority of the core functionalities operate correctly and reliably. Essential features such as authentication, dashboard viewing, pond management, water quality monitoring, visual alerts, biometric growth tracking, feed and expense tracking, FCR calculation, and role-based access control successfully support the primary objectives of the app.

However, the application is not yet fully ready for full release because the offline data entry requirement did not fully pass. During scenario-based testing, the app accepted feed data input while offline, but the entry could not be saved locally until internet connection was restored. This issue may negatively affect field use because technicians are expected to record pond data in areas with unstable internet connection.

The application is suitable for beta or limited release, but the offline saving and syncing behavior should be fixed before full deployment.

---

## Remarks

PondStat presents a practical and useful solution for aquaculture students and pond monitoring personnel. Its dashboard, pond management tools, water quality logging, biometric tracking, and FCR calculation features are aligned with the needs of users who previously relied on multiple Excel sheets.

Recommended improvements include:

- Add clearer instructions or visible controls for editing and deleting ponds.
- Clean up default or leftover custom parameters such as "d", "dd", and "fef" for newly created accounts.
- Fix offline feed entry saving so new records are cached locally without requiring an internet connection.
- Make user roles more visible in the interface.
- Ensure the "add collaborators" tab remains consistent and does not disappear unexpectedly after adding another pond.
- Add clearer confirmation prompts for risky actions such as pond deletion.
- Improve onboarding or help text for first-time users.

These improvements would help make the app more reliable, understandable, and suitable for full release.