# 📋 Release Testing

## a. Target App Summary

**App Name:** PondStat

PondStat is a Flutter-based mobile application designed to help aquaculture students, specifically F125 students, transition from managing data in multiple Excel sheets to a unified and efficient digital platform.

The app solves problems such as data loss from scattered spreadsheets, difficulty in historical analysis, and delayed response to critical pond conditions. PondStat allows users to manage ponds, monitor water quality, record biometric sampling data, track feed consumption and expenses, and work offline while syncing data once internet connection is restored.

The app supports two main user roles: **Farm Owner** and **Technician**.

**Core Features:**

1. Real-time Parameter Monitoring
2. Biometric Growth Tracking
3. Feed and Expense Tracking with FCR Calculation
4. Offline Support
5. Role-Based Access Control

---

## b. Requirements List

1. The app shall authenticate users securely via Google Sign-In, restricted to authorized accounts.

2. The app shall display a dashboard providing a high-level overview of all active ponds, current culture periods, and key statistics.

3. The app shall allow users to create, edit, and delete ponds, with deletion triggering a cascading removal of all associated data, including measurements, feed logs, and finances.

4. The app shall allow users to log water quality parameters such as pH, dissolved oxygen, temperature, and salinity.

5. The app shall display visual alerts when water quality parameter values fall outside acceptable ranges.

6. The app shall allow users to record biometric sampling data.

7. The app shall visualize growth curves and provide biomass estimates over time based on biometric data.

8. The app shall allow users to track daily feed consumption and related expenses, and calculate Feed Conversion Ratio (FCR).

9. The app shall support offline data entry by caching operations locally and automatically syncing pending data to the cloud upon reconnection.

10. The app shall enforce role-based access control by distinguishing between Farm Owner and Technician permission levels.

---

## c. Requirements-Based Testing

---

### REQUIREMENT #1

| Field | Description |
|---|---|
| **Requirement** | The app shall authenticate users securely via Google Sign-In, restricted to authorized accounts. |
| **Test Input / Action** | Open the app and attempt to sign in using the whitelisted Google reviewer account. Then attempt to sign in using a non-authorized Google account. |
| **Expected Result** | The authorized account should successfully log in and access the app. The unauthorized account should be denied access and should not be redirected to the dashboard. |
| **Actual Result** | The app successfully authenticated the authorized account via Google Sign-In and granted access. The unauthorized account was denied and could not proceed to the dashboard. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #2

| Field | Description |
|---|---|
| **Requirement** | The app shall display a dashboard providing a high-level overview of all active ponds, current culture periods, and key statistics. |
| **Test Input / Action** | Log in to the app and navigate to the Dashboard. Observe the pond cards, active ponds, culture period details, and displayed statistics. |
| **Expected Result** | The dashboard should load successfully and display all active ponds, their current culture periods, and key statistics such as species, stocking date, age of culture, or other available summary data. |
| **Actual Result** | The dashboard loaded and showed all active ponds along with their culture periods and key statistics including species, stocking date, and age of culture. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #3

| Field | Description |
|---|---|
| **Requirement** | The app shall allow users to create, edit, and delete ponds, with deletion triggering a cascading removal of all associated data, including measurements, feed logs, and finances. |
| **Test Input / Action** | Create a test pond, edit its details, add sample measurements, feed logs, and finance records, then delete the pond. Check whether the pond and all associated records are removed. |
| **Expected Result** | The user should be able to create and edit pond records. When the pond is deleted, it should be removed from the dashboard and all related measurements, feed logs, and finance records should also be removed. |
| **Actual Result** | Pond creation and editing worked as expected. Deleting the pond removed it from the dashboard along with all associated measurements, feed logs, and finance records. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #4

| Field | Description |
|---|---|
| **Requirement** | The app shall allow users to log water quality parameters such as pH, dissolved oxygen, temperature, and salinity. |
| **Test Input / Action** | Open an existing pond, navigate to the Water Quality section, enter valid values for pH, dissolved oxygen, temperature, and salinity, then save the entry. |
| **Expected Result** | The water quality entry should be saved successfully and displayed under the selected pond's monitoring records. |
| **Actual Result** | The water quality entry was saved and correctly displayed under the pond's monitoring records. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #5

| Field | Description |
|---|---|
| **Requirement** | The app shall display visual alerts when water quality parameter values fall outside acceptable ranges. |
| **Test Input / Action** | Open the Water Quality section and enter an abnormal water quality value, such as critically low dissolved oxygen or an out-of-range pH value. Save the entry and observe the displayed record. |
| **Expected Result** | The app should display a clear visual alert, warning indicator, color change, or warning message showing that the entered value is outside the acceptable range. |
| **Actual Result** | The app displayed a visual alert and color indicator notifying that the entered value was outside the acceptable range. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #6

| Field | Description |
|---|---|
| **Requirement** | The app shall allow users to record biometric sampling data. |
| **Test Input / Action** | Open the Biometric Growth section of a pond and enter biometric sampling data such as sample count, average weight, or other available measurement fields. Save the entry. |
| **Expected Result** | The biometric sampling data should be saved successfully and displayed under the selected pond's biometric records. |
| **Actual Result** | The biometric sampling data was saved and appeared under the pond's biometric records without issue. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #7

| Field | Description |
|---|---|
| **Requirement** | The app shall visualize growth curves and provide biomass estimates over time based on biometric data. |
| **Test Input / Action** | Add at least two biometric sampling records on different dates, then open the growth visualization or analytics section. |
| **Expected Result** | The app should display a growth curve based on the recorded biometric data and provide a biomass estimate over time. |
| **Actual Result** | The app showed a growth curve and biomass estimates based on the biometric records entered on different dates. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #8

| Field | Description |
|---|---|
| **Requirement** | The app shall allow users to track daily feed consumption and related expenses, and calculate Feed Conversion Ratio (FCR). |
| **Test Input / Action** | Open the Feed, Operations, or Finances section. Enter a daily feed consumption record and related expense, then check whether the app displays or calculates the Feed Conversion Ratio. |
| **Expected Result** | The feed consumption and expense records should be saved successfully. The app should display or calculate the Feed Conversion Ratio based on the available feed and growth data. |
| **Actual Result** | Feed consumption and expense records were saved successfully. The app computed and displayed the FCR based on the available data. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #9

| Field | Description |
|---|---|
| **Requirement** | The app shall support offline data entry by caching operations locally and automatically syncing pending data to the cloud upon reconnection. |
| **Test Input / Action** | Enable airplane mode or disconnect the device from the internet. Add a new monitoring or feed record while offline. Reconnect to the internet and observe whether the data syncs automatically. |
| **Expected Result** | The app should show an offline indicator or banner. The entry should be saved locally while offline. Once internet connection returns, the pending data should automatically sync to the cloud without requiring manual action. |
| **Actual Result** | The app displayed an offline banner and saved the entry locally. Upon reconnection, the data synced to the cloud automatically. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #10

| Field | Description |
|---|---|
| **Requirement** | The app shall enforce role-based access control by distinguishing between Farm Owner and Technician permission levels. |
| **Test Input / Action** | Log in using a Technician account and attempt to perform a Farm Owner-only action, such as deleting a pond or modifying restricted farm-level settings. |
| **Expected Result** | The app should prevent the Technician from performing restricted actions and display a clear permission-denied message. |
| **Actual Result** | The app blocked the Technician from performing restricted actions and showed a permission-denied message. |
| **Pass / Fail** | PASS |

## d. Scenario-Based Testing

---

### Scenario 1: Farm Owner monitors a pond and responds to a water quality alert

**User Story:**  
As a Farm Owner, I want to monitor my pond's water quality and be alerted to dangerous readings, so that I can act quickly and prevent possible stock loss.

| Step | Action | Expected Behavior | Result | Remarks |
|---|---|---|---|---|
| 1 | Open the app and log in using the Farm Owner account. | Dashboard loads and shows all active ponds. | Dashboard loaded successfully and displayed all active ponds. | PASS |
| 2 | Tap on an active pond to open its details. | Pond detail view opens successfully with monitoring sections. | Pond detail view opened successfully with all monitoring sections visible. | PASS |
| 3 | Navigate to the Water Quality section. | Water Quality section loads with previous parameter entries and an option to add a new entry. | Water Quality section loaded with existing entries and the option to add a new entry. | PASS |
| 4 | Tap "Add Entry" and input a dissolved oxygen value of 2.0 mg/L. | The input form accepts the value. | The input form accepted the dissolved oxygen value of 2.0 mg/L without issue. | PASS |
| 5 | Save the parameter entry. | The entry is saved successfully. | The entry was saved successfully and appeared in the monitoring records. | PASS |
| 6 | Observe the saved dissolved oxygen value. | The DO value is flagged with a visual alert indicating that it is below the safe threshold. | A visual alert was displayed indicating the DO value is below the safe threshold. | PASS |
| 7 | Navigate back to the Dashboard. | Dashboard still reflects the active pond and no data loss is observed. | Dashboard reflected the active pond correctly with no data loss observed. | PASS |

---

### Scenario 2: Technician logs feed data while offline

**User Story:**  
As a Technician at the pond edge, I want to log daily feed consumption even without internet access, so that no data is lost due to connectivity issues in the field.

| Step | Action | Expected Behavior | Result | Remarks |
|---|---|---|---|---|
| 1 | Open the app and log in using the Technician account while connected to the internet. | The user is authenticated and redirected to the dashboard. | The Technician account was authenticated successfully and redirected to the dashboard. | PASS |
| 2 | Enable airplane mode on the device. | Network connection is disabled and the app displays an offline status banner. | Network connection was disabled and the app displayed an offline status banner. | PASS |
| 3 | Open an existing pond record. | Previously loaded or cached pond data remains accessible. | Previously loaded pond data remained accessible while offline. | PASS |
| 4 | Navigate to the Feed, Operations, or Finances section. | The section opens and allows the user to input feed-related data. | The section opened and allowed input of feed-related data while offline. | PASS |
| 5 | Tap "Add Feed Entry" and input 5 kg of feed with a cost of ₱250. | The form accepts the values while offline. | The form accepted the values of 5 kg of feed and ₱250 while offline. | PASS |
| 6 | Save the feed entry. | The entry is saved locally and a confirmation is shown despite being offline. | The entry was saved locally and a confirmation was shown while offline. | PASS |
| 7 | Disable airplane mode to restore connectivity. | The app detects reconnection and automatically syncs the pending entry to Firestore. | The app detected reconnection and automatically synced the pending entry to Firestore. | PASS |
| 8 | Refresh or reopen the pond record. | The newly added feed entry remains visible after syncing. | The newly added feed entry remained visible after syncing. | PASS |

---

## e. Summary

### Testing Summary

**Requirements-Based Testing** covered all 10 defined requirements across the app's core functionality, including authentication, dashboard display, pond management, water quality logging, visual alerts, biometric sampling, growth visualization, feed and expense tracking, offline support, and role-based access control.

A total of 10 out of 10 requirements passed, while 0 requirement/s failed.

**Scenario-Based Testing** validated two realistic end-to-end user workflows. The first scenario tested a Farm Owner monitoring pond water quality and responding to a critical dissolved oxygen alert. The second scenario tested a Technician logging feed data while offline and syncing the pending entry after reconnection.

A total of 2 out of 2 scenarios were completed successfully.

---

### Requirements-Based Testing Result

| Requirement No. | Requirement Summary | Result |
|---|---|---|
| 1 | Google Sign-In authentication restricted to authorized accounts | PASS |
| 2 | Dashboard overview of active ponds, culture periods, and key statistics | PASS |
| 3 | Create, edit, and delete ponds with cascading deletion | PASS |
| 4 | Log water quality parameters | PASS |
| 5 | Display visual alerts for abnormal water quality values | PASS |
| 6 | Record biometric sampling data | PASS |
| 7 | Visualize growth curves and biomass estimates | PASS |
| 8 | Track feed consumption, expenses, and FCR | PASS |
| 9 | Offline data entry and automatic cloud syncing | PASS |
| 10 | Role-based access control | PASS |

---

### Scenario-Based Testing Result

| Scenario No. | Scenario Summary | Result |
|---|---|---|
| 1 | Farm Owner monitors water quality and responds to alert | PASS |
| 2 | Technician records feed data while offline | PASS |

---

### Conclusion

Based on the release testing conducted, **PondStat is ready for release**.

The application passed all 10 requirements and completed both scenario-based tests successfully. Core functions including authentication, pond management, water quality monitoring, offline syncing, and role-based access control all performed as expected. PondStat is confirmed ready for release.

---

### Remarks

Overall, PondStat demonstrated stable performance across its core features during release testing. Authentication, pond management, water quality monitoring, biometric tracking, growth visualization, and role-based access control all functioned as expected. The overall UI/UX is very good, with a clean and intuitive interface that makes navigation straightforward for both Farm Owners and Technicians.