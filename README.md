# 🏸 Badminton Sports Event Manager

A comprehensive, responsive, and user-friendly web application designed to simplify badminton player registration and tournament management.

Whether you are organizing a university sports week or a local club tournament, this application helps players register for singles or doubles matches, check their fee status, and manage their profiles. Organizers can manage participants through a dedicated management dashboard.

---

## ✨ Features

### 👤 For Players

- **Dynamic Registration:** The registration form adapts to the selected category. Doubles registration requires partner details.
- **Duplicate Prevention:** Prevents the same AG Number from being registered more than once in the same category.
- **Player Portal:** Players can log in using their AG Number to view their profiles, check fee status, and edit their details.
- **Fee Instructions:** Unpaid players can view banking instructions to pay their registration fees.

### 🛡️ For Management (Organizers)

- **Role-Based Player Filtering:** Different management passwords provide different player views:
  - `manag123` — View all players.
  - `managmale` — View male players only.
  - `managfemale` — View female players only.
- **Centralized Dashboard:** View, edit, delete, and update the payment status of registered players.
- **Smart Search and Filters:** Search players by name or AG Number and filter by singles, doubles, paid, or unpaid status.
- **CSV Export:** Export filtered player records to a CSV file for use in spreadsheet applications.
- **CSV Import:** Import player records from a CSV file for bulk registration.

> **Security note:** The management passwords described above must not be treated as secure authentication if they are stored in client-side JavaScript. Use proper authentication and server-side or Firebase Security Rules for real access control.

---

## 🛠️ Technologies Used

- **HTML5:** Defines the structure of the application.
- **Tailwind CSS:** Provides responsive styling through a CDN.
- **JavaScript (ES6 Modules):** Handles application logic and modular imports.
- **Firebase Realtime Database:** Stores and synchronizes player data.
- **Git and GitHub:** Used for version control and project hosting.

---

## 🚀 Setup and Installation

Follow these steps to run the project on your local computer.

### Step 1: Create a Firebase Account and Project

1. Visit the [Firebase Console](https://console.firebase.google.com/).
2. Sign in using your Google account.
3. Click **Create a project** or **Add project**.
4. Enter a project name, such as `Badminton Event`.
5. Follow the instructions to create your project.
6. Google Analytics is optional for this application. You can disable it if you do not need it.
7. Click **Continue** when your project is ready.

### Step 2: Create Firebase Realtime Database

1. Open your Firebase project.
2. Navigate to **Build → Realtime Database**.
3. Click **Create Database**.
4. Select a database location.
5. Follow the setup instructions to create the database.
6. Open the **Rules** tab to configure database access.

**Important security warning:** Do not use public read/write rules for a publicly deployed application. Rules such as the following allow anyone to read and modify your database:

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

These rules may be useful for understanding a temporary test setup, but they expose your player data to unauthorized access. Configure appropriate Firebase Authentication and Realtime Database Security Rules before using the application with real player information.

Click **Publish** after configuring the appropriate rules.

### Step 3: Get Your Firebase Configuration

1. Open **Project Overview** in the Firebase Console.
2. Click the **Web icon (`</>`)** to register a web application.
3. Enter an app nickname, such as `Badminton App`.
4. Click **Register app**.
5. Firebase will display your web app configuration.
6. Copy the configuration values, including the fields required by your project, such as `apiKey`, `authDomain`, `databaseURL`, `projectId`, `storageBucket`, `messagingSenderId`, and `appId`.

Some fields may be optional depending on your Firebase setup. Use the values provided for your own project.

### Step 4: Download the Repository

Clone the repository using Git:

```bash
git clone YOUR_REPOSITORY_URL
cd badminton-sports-event-manager
```

Replace `YOUR_REPOSITORY_URL` with your actual GitHub repository URL.

Alternatively, download the repository as a ZIP file and extract it.

### Step 5: Configure Your Firebase Keys

The original `firebase-config.js` file is excluded from the public repository. You must create your own local configuration file.

1. Locate `firebase-config.example.js` in the project folder.
2. Create a copy of this example file.
3. Rename the copied file to exactly `firebase-config.js`.
4. Open `firebase-config.js` in your code editor.
5. Replace the placeholder values with the configuration values from your own Firebase project.
6. Save the file.

For example, your configuration file should follow this structure:

```javascript
// firebase-config.js
export const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
    databaseURL: "YOUR_DATABASE_URL",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_STORAGE_BUCKET",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
};
```

Use your actual Firebase values instead of the placeholders. Keep the fields consistent with the configuration expected by your project.

**Remember:** `firebase-config.js` is a local file. Do not upload it to your public GitHub repository.

### Step 6: Protect Your Configuration File with `.gitignore`

To prevent Git from tracking your local configuration file:

1. Create a file named `.gitignore` in the root of the project.
2. Add the following line:

```text
firebase-config.js
```

3. Save the file.

This instructs Git to ignore the configuration file when it is not already tracked.

If the file was committed previously, adding it to `.gitignore` alone will not remove it from Git history. Remove it from tracking and address any exposed credentials or sensitive data separately.

### Step 7: Run the Application

Because the application uses JavaScript ES6 modules, opening `index.html` directly by double-clicking it may cause browser module-loading or CORS errors.

1. Install [Visual Studio Code](https://code.visualstudio.com/) if necessary.
2. Open the project folder in VS Code.
3. Install the **Live Server** extension.
4. Right-click `index.html`.
5. Select **Open with Live Server**.
6. Test the registration form, player portal, management dashboard, and Firebase connection.

The application should now run in your browser, provided the configuration and database permissions are correct.

---

## 📁 Project Structure

```text
badminton-sports-event-manager/
│
├── .gitignore
├── index.html
├── firebase-config.example.js
├── README.md
│
└── firebase-config.js  # Local file only; not uploaded to GitHub
```

The `firebase-config.js` file is created by each user on their own computer and is excluded from the public repository through `.gitignore`.

---

## 🔐 Security Guidelines

- Create and use your own Firebase project.
- Never upload your local `firebase-config.js` file to GitHub.
- Keep `firebase-config.example.js` free of real credentials.
- Configure Firebase Security Rules to control access to player records.
- Use Firebase Authentication and appropriate authorization for management features.
- Do not store passwords or private service account keys in frontend code.
- Remember that Firebase web configuration is visible to users of a browser-based application. The configuration file being absent from GitHub does not, by itself, secure the database.

---

## 🎯 Project Purpose

The purpose of this project is to make badminton tournament registration and participant management easier, faster, and more organized for universities, sports clubs, and tournament organizers.

## 👨‍💻 Author

**Hafiz Hasnain Mughal**

