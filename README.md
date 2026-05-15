# PondStat Mobile App

PondStat is a comprehensive mobile application built with Flutter, designed to help aquaculture farmers and students efficiently manage and monitor their ponds. Whether farming Shrimp or Tilapia, PondStat provides tools for tracking pond growth, monitoring water quality parameters, managing daily feed consumption and expenses, supporting offline data entry, and analyzing pond performance.

This README also contains the **CMSC 129 Activity 3 Release Testing** documentation for PondStat.

---

## 🌟 Key Features

* **Dashboard:** Provides a high-level overview of all active ponds, current culture periods, and key statistics.
* **Pond Management:** Allows users to create, edit, and delete ponds, including associated measurements, feed logs, and finance records.
* **Parameter Monitoring:** Allows users to log essential water quality parameters such as pH, dissolved oxygen, temperature, and salinity.
* **Visual Alerts:** Displays alerts when water quality values fall outside acceptable ranges.
* **Biometric Growth Tracking:** Allows users to record sampling data and track growth over time.
* **Growth Visualization:** Displays growth curves and provides biomass estimates based on biometric records.
* **Feed and Expense Tracking:** Allows users to track daily feed consumption, related expenses, and Feed Conversion Ratio (FCR).
* **Offline Support:** Allows local data entry when there is no internet connection and automatically syncs pending data once connectivity returns.
* **Role-Based Access Control:** Differentiates access levels between Farm Owners and Technicians.
* **Authentication:** Uses secure Google Sign-In restricted to authorized accounts.

---

## 🛠 Tech Stack

* **Framework:** Flutter (Dart)
* **Backend:** Firebase
  * Firestore Database
  * Firebase Authentication
  * Firebase Storage
  * Firebase Messaging
* **Cloud Functions:** Firebase Cloud Functions
* **State Management:** Riverpod / flutter_riverpod
* **Local Storage / Offline Support:** Firestore local caching and local persistence
* **Architecture:** Feature-based folder structure with separation of concerns

---

## 📁 Project Structure

The project follows a clean, feature-centric directory structure inside the `lib/` folder:

```text
lib/
├── core/                   # Shared resources, widgets, themes, and firebase/network helpers
│   ├── error/
│   ├── firebase/
│   ├── network/
│   ├── services/
│   ├── theme/
│   ├── utils/
│   └── widgets/            # Reusable UI components
├── features/               # Main application features
│   ├── auth/               # User authentication and onboarding
│   ├── dashboard/          # Main landing view and pond summaries
│   ├── monitoring/         # Water quality, growth, feed, and finance tracking
│   └── profile/            # User settings and profile management
└── main.dart               # Application entry point
```

---

## 🚀 Getting Started

To get a local copy up and running, follow these steps.

### Prerequisites

* Install Flutter SDK v3.19.0 or higher
* Install Dart 3.3 or higher
* Install Node.js v18 or higher
* Install Firebase CLI
* Install an IDE such as Android Studio, IntelliJ IDEA, or VS Code with Flutter plugins
* Use a connected physical device or emulator
* Supported devices:
  * iOS 14.0 or higher
  * Android API 24 or higher

### Installation

1. **Clone the repository**

   ```sh
   git clone https://github.com/your-username/PondStat-Mobile-App.git
   cd PondStat-Mobile-App
   ```

2. **Install dependencies**

   ```sh
   flutter pub get
   ```

3. **Firebase Configuration**

   This project requires Firebase to function.

   * Create a Firebase project in the Firebase Console.
   * Enable Firestore.
   * Enable Firebase Authentication.
   * Enable Firebase Storage.
   * Enable Firebase Messaging.
   * Activate the FlutterFire CLI:

     ```sh
     dart pub global activate flutterfire_cli
     ```

   * Configure the app for Firebase:

     ```sh
     flutterfire configure
     ```

   * This will generate the required `firebase_options.dart` and native configuration files.

4. **Cloud Functions**

   If Cloud Functions are used, navigate to the functions directory and run:

   ```sh
   cd functions
   npm install
   npm run build
   firebase deploy --only functions
   ```

5. **Run the application**

   ```sh
   flutter run
   ```

---

## 🧪 Testing

The project may include widget and unit tests to ensure UI reliability and business logic correctness.

To run the test suite:

```sh
flutter test
```

---

## 🎨 Theming & Styling

PondStat uses Material 3 theming and reusable UI components. The application defines custom color schemes, typography, and shared widgets to maintain a consistent interface across the app.

---

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
| **Actual Result** | The app authenticate users securely via Google Sign-In. I successfully log in and access the app. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #2

| Field | Description |
|---|---|
| **Requirement** | The app shall display a dashboard providing a high-level overview of all active ponds, current culture periods, and key statistics. |
| **Test Input / Action** | Log in to the app and navigate to the Dashboard. Observe the pond cards, active ponds, culture period details, and displayed statistics. |
| **Expected Result** | The dashboard should load successfully and display all active ponds, their current culture periods, and key statistics such as species, stocking date, age of culture, or other available summary data. |
| **Actual Result** | The dashboard load successfully and display all active ponds, their current culture periods, and key statistics such as species, stocking date, age of culture, or other available summary data. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #3

| Field | Description |
|---|---|
| **Requirement** | The app shall allow users to create, edit, and delete ponds, with deletion triggering a cascading removal of all associated data, including measurements, feed logs, and finances. |
| **Test Input / Action** | Create a test pond, edit its details, add sample measurements, feed logs, and finance records, then delete the pond. Check whether the pond and all associated records are removed. |
| **Expected Result** | The user should be able to create and edit pond records. When the pond is deleted, it should be removed from the dashboard and all related measurements, feed logs, and finance records should also be removed. |
| **Actual Result** | The user CAN be able to create and edit pond records. When the pond is deleted, it should be removed from the dashboard and all related measurements, feed logs, and finance records should also be removed. The only issue is that there is no instruction yet as the edit/delete function of the pond is hidden. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #4

| Field | Description |
|---|---|
| **Requirement** | The app shall allow users to log water quality parameters such as pH, dissolved oxygen, temperature, and salinity. |
| **Test Input / Action** | Open an existing pond, navigate to the Water Quality section, enter valid values for pH, dissolved oxygen, temperature, and salinity, then save the entry. |
| **Expected Result** | The water quality entry should be saved successfully and displayed under the selected pond's monitoring records. |
| **Actual Result** | The water quality entry saved successfully and displayed under the selected pond's monitoring records. There is an issue with the database because some custom-made parameters name "d","dd","fef" is still visible even if I just made the account. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #5

| Field | Description |
|---|---|
| **Requirement** | The app shall display visual alerts when water quality parameter values fall outside acceptable ranges. |
| **Test Input / Action** | Open the Water Quality section and enter an abnormal water quality value, such as critically low dissolved oxygen or an out-of-range pH value. Save the entry and observe the displayed record. |
| **Expected Result** | The app should display a clear visual alert, warning indicator, color change, or warning message showing that the entered value is outside the acceptable range. |
| **Actual Result** | The app should a clear visual alert, warning indicator, color change, or warning message showing that the entered value is outside the acceptable range. When it is out of range the app notifies. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #6

| Field | Description |
|---|---|
| **Requirement** | The app shall allow users to record biometric sampling data. |
| **Test Input / Action** | Open the Biometric Growth section of a pond and enter biometric sampling data such as sample count, average weight, or other available measurement fields. Save the entry. |
| **Expected Result** | The biometric sampling data should be saved successfully and displayed under the selected pond's biometric records. |
| **Actual Result** |  The biometric sampling data saved successfully and displayed under the selected pond's biometric records. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #7

| Field | Description |
|---|---|
| **Requirement** | The app shall visualize growth curves and provide biomass estimates over time based on biometric data. |
| **Test Input / Action** | Add at least two biometric sampling records on different dates, then open the growth visualization or analytics section. |
| **Expected Result** | The app should display a growth curve based on the recorded biometric data and provide a biomass estimate over time. |
| **Actual Result** | The app display a growth curve based on the recorded biometric data and provide a biomass estimate over time. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #8

| Field | Description |
|---|---|
| **Requirement** | The app shall allow users to track daily feed consumption and related expenses, and calculate Feed Conversion Ratio (FCR). |
| **Test Input / Action** | Open the Feed, Operations, or Finances section. Enter a daily feed consumption record and related expense, then check whether the app displays or calculates the Feed Conversion Ratio. |
| **Expected Result** | The feed consumption and expense records should be saved successfully. The app should display or calculate the Feed Conversion Ratio based on the available feed and growth data. |
| **Actual Result** | The feed consumption and expense records saved successfully. The app displays/calculates the Feed Conversion Ratio based on the available feed and growth data. There is an issue when offline, the save button is only loading until there is connection again. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #9

| Field | Description |
|---|---|
| **Requirement** | The app shall support offline data entry by caching operations locally and automatically syncing pending data to the cloud upon reconnection. |
| **Test Input / Action** | Enable airplane mode or disconnect the device from the internet. Add a new monitoring or feed record while offline. Reconnect to the internet and observe whether the data syncs automatically. |
| **Expected Result** | The app should show an offline indicator or banner. The entry should be saved locally while offline. Once internet connection returns, the pending data should automatically sync to the cloud without requiring manual action. |
| **Actual Result** | The app support offline data. The app shows an offline indicator or banner but the saved datas are still visible. |
| **Pass / Fail** | PASS |

---

### REQUIREMENT #10

| Field | Description |
|---|---|
| **Requirement** | The app shall enforce role-based access control by distinguishing between Farm Owner and Technician permission levels. |
| **Test Input / Action** | Log in using a Technician account and attempt to perform a Farm Owner-only action, such as deleting a pond or modifying restricted farm-level settings. |
| **Expected Result** | The app should prevent the Technician from performing restricted actions and display a clear permission-denied message. |
| **Actual Result** | The app prevents the Technician from performing restricted actions and display a clear permission-denied message. But the app doesn't visibly show the roles. It only shows in your profile with the "add collaborators" tab when you have only 1 pond. Adding pond fully remove the "add collaborators" tab|
| **Pass / Fail** | PASS |

---

## d. Scenario-Based Testing

---

### Scenario 1: Farm Owner monitors a pond and responds to a water quality alert

**User Story:**  
As a Farm Owner, I want to monitor my pond's water quality and be alerted to dangerous readings, so that I can act quickly and prevent possible stock loss.

| Step | Action | Expected Behavior | Result | Remarks |
|---|---|---|---|---|
| 1 | Open the app and log in using the Farm Owner account. | Dashboard loads and shows all active ponds. | | PASS |
| 2 | Tap on an active pond to open its details. | Pond detail view opens successfully with monitoring sections. | | PASS |
| 3 | Navigate to the Water Quality section. | Water Quality section loads with previous parameter entries and an option to add a new entry. | | PASS |
| 4 | Tap "Add Entry" and input a dissolved oxygen value of 2.0 mg/L. | The input form accepts the value. |  | PASS |
| 5 | Save the parameter entry. | The entry is saved successfully. |  | PASS |
| 6 | Observe the saved dissolved oxygen value. | The DO value is flagged with a visual alert indicating that it is below the safe threshold. | | PASS |
| 7 | Navigate back to the Dashboard. | Dashboard still reflects the active pond and no data loss is observed. |  | PASS |

---

### Scenario 2: Technician logs feed data while offline

**User Story:**  
As a Technician at the pond edge, I want to log daily feed consumption even without internet access, so that no data is lost due to connectivity issues in the field.

| Step | Action | Expected Behavior | Result | Remarks |
|---|---|---|---|---|
| 1 | Open the app and log in using the Technician account while connected to the internet. | The user is authenticated and redirected to the dashboard. |  | PASS |
| 2 | Enable airplane mode on the device. | Network connection is disabled and the app displays an offline status banner. |  | PASS |
| 3 | Open an existing pond record. | Previously loaded or cached pond data remains accessible. |  | PASS |
| 4 | Navigate to the Feed, Operations, or Finances section. | The section opens and allows the user to input feed-related data. |  | PASS  |
| 5 | Tap "Add Feed Entry" and input 5 kg of feed with a cost of ₱250. | The form accepts the values while offline. | The form does accept values offline but it can’t save. | FAIL |
| 6 | Save the feed entry. | The entry is saved locally and a confirmation is shown despite being offline. | The entry is not saved locally while being offline. | FAIL |
| 7 | Disable airplane mode to restore connectivity. | The app detects reconnection and automatically syncs the pending entry to Firestore. |  | PASS |
| 8 | Refresh or reopen the pond record. | The newly added feed entry remains visible after syncing. |  | PASS |

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

Based on the release testing conducted, **PondStat is [ready / not yet ready] for release**.

The application passed 10 out of 10 requirements and completed 2 out of 2 scenario-based tests. The final release decision should be based on the actual testing results, especially whether the core functions such as authentication, pond management, monitoring, offline syncing, and role-based access control worked as expected.

---

### Remarks

[Input final remarks here based on the actual testing experience, observed issues, UI/UX comments, limitations, and recommendations.]

---

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create.

1. Fork the Project
2. Create your Feature Branch

   ```sh
   git checkout -b feature/AmazingFeature
   ```

3. Commit your Changes

   ```sh
   git commit -m 'Add some AmazingFeature'
   ```

4. Push to the Branch

   ```sh
   git push origin feature/AmazingFeature
   ```

5. Open a Pull Request

