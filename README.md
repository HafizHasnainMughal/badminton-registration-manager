```markdown
# 🏸 Badminton Sports Event Manager

A comprehensive, responsive, and professional web-based application designed to streamline player registrations and tournament management. 

Whether organizing a university sports week or a local club tournament, this system allows players to easily register for singles or doubles matches, track their fee status, and manage their profiles. It also features a secure, role-based management dashboard for organizers to filter, edit, and export participant data.

---

## ✨ Comprehensive Features

### 👤 For Players
* **Dynamic Registration:** Smart form that adapts based on the selected category. If "Doubles" is selected, partner details are dynamically required.
* **Duplicate Prevention:** Built-in validation ensures that a unique AG Number cannot be registered twice in the same category.
* **Player Portal:** Returning players can log in using their AG Number to view their complete profile, check their payment status, and edit their details.
* **Automated Fee Instructions:** Unpaid players receive automatic banking instructions to clear their dues.

### 🛡️ For Management (Organizers)
* **Role-Based Password Filtering System:** A unique login mechanism where the password used determines the data visibility:
  * Log in with `manag123` ➔ View **All Players**
  * Log in with `managmale` ➔ View **Male Players Only**
  * Log in with `managfemale` ➔ View **Female Players Only**
* **Centralized Dashboard:** A complete overview of all registrations with one-click inline actions (Pay/Unpay, Edit, Delete).
* **Smart Search & Sub-Filters:** Instantly search by Name or AG Number, and apply secondary filters (Singles, Doubles, Paid, Unpaid).
* **Data Portability (CSV):** Export the current filtered list to a `.csv` file for offline spreadsheet use, or import a `.csv` file to bulk-add players.

---

## 🛠️ Technologies Used
* **Frontend:** HTML5, Tailwind CSS (via CDN for rapid, modern UI styling).
* **Logic:** Vanilla JavaScript utilizing ES6 Modules (`import`/`export`).
* **Database:** Firebase Realtime Database (BaaS) for secure, real-time data synchronization.

---

## 🚀 Setup & Installation Instructions

**⚠️ SECURITY WARNING:** To keep the database secure, the actual Firebase configuration keys are NOT included in this repository. 

To run this project on your local machine, follow these step-by-step instructions from scratch:

### 1. How to Login & Create a Firebase Project
If you are completely new to Firebase, follow these steps to set up your account and project:
1. Go to the [Firebase Website](https://firebase.google.com/) and click **"Sign In"** at the top right corner. Log in using your normal Google (Gmail) account.
2. Once logged in, click on **"Go to console"** at the top right.
3. Click on the large box that says **"Add Project"** (or "Create a Project").
4. Enter a name for your project (e.g., "Badminton Event"), check the terms box, and click **Continue**.
5. On the Google Analytics page, you can turn the toggle **OFF** (to keep things simple) and click **Create Project**. 
6. Wait a few seconds for the project to build, then click **Continue**.

### 2. How to Create the Database & Edit Read/Write Rules
Now that you are inside your project dashboard, you need to create the database and allow data to be entered and read:
1. Look at the left sidebar menu. Expand the **Build** menu and click on **Realtime Database**.
2. Click the **"Create Database"** button.
3. Choose a server location (the default is fine) and click **Next**.
4. Select **"Start in test mode"** and click **Enable**. Your database is now created!
5. **CRUCIAL STEP - Edit Rules:** To ensure your app can successfully enter (write) and display (read) data, click on the **"Rules"** tab at the top of the database page.
6. Edit the code inside the box to look exactly like this (changing false to true if needed):
   ```json
   {
     "rules": {
       ".read": true,
       ".write": true
     }
   }

```

7. Click the **"Publish"** button. Now your database is fully ready to accept and read player registrations!

### 3. How to Get Your Configuration Keys

To connect this code to your new database:

1. Go back to the **Project Overview** (click the home icon on the top left sidebar).
2. You will see text saying "Get started by adding Firebase to your app". Click on the **Web icon (`</>`)**.
3. Type an app nickname (e.g., "Badminton App") and click **"Register app"**.
4. In the second step, you will see a block of code with `const firebaseConfig = { ... }`.
5. **Copy all the keys inside those brackets** (including `apiKey`, `authDomain`, `databaseURL`, `projectId`, etc.).

### 4. Configure the Application Locally

1. Clone this repository to your local machine:
```bash
git clone <YOUR_REPOSITORY_URL>
cd badminton-sports-event-manager

```


2. Locate the dummy file named `firebase-config.example.js`.
3. Create a **new** file in the same folder and name it exactly `firebase-config.js`.
4. Open the new `firebase-config.js` file and **paste the keys you copied from Firebase** here, replacing the placeholder text (`YOUR_API_KEY`, etc.).

### 5. Secure your Keys (Crucial Step)

Before uploading any of your own changes to GitHub, you must prevent Git from tracking your private keys:

1. Create a file named `.gitignore` in the root of your project.
2. Add the following line to it:
```text
firebase-config.js

```



### 6. Run the Application

Because this project utilizes modern ES6 Modules (`type="module"`), the browser will block the script due to CORS policies if you simply double-click the `index.html` file.

1. Open the project folder in a code editor like **Visual Studio Code**.
2. Install a local server extension (such as the **Live Server** extension).
3. Right-click `index.html` and select **"Open with Live Server"**. The app will launch safely in your default browser.

---

## 📁 Project Structure

```text
badminton-sports-event-manager/
├── .gitignore                   # Ignores private config files
├── index.html                   # Main application interface and UI
├── firebase-config.example.js   # Dummy template for GitHub
├── firebase-config.js           # YOUR actual database keys (Do not upload!)
└── README.md                    # Project documentation

```

```

Maine **Step 2** ko poori tarah update kar diya hai. Ab isme explicitly mention kar diya gaya hai ke database create karne ke baad **"Rules"** tab mein jaa kar `".read": true` aur `".write": true` karna kitna zaroori hai. Iske baghair app mein data enter (write) ya display (read) nahi ho sakta tha. Saath mein JSON format code bhi de diya hai aur **Publish** button click karne ka instruction bhi shamil kar diya hai taake kisi ko confusion na ho!

```