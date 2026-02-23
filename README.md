<h1 align="center">
  Taskmanager & AssetManagement App
</h1>

<p align="center">
  A comprehensive Android application built with Kotlin for efficient task tracking and asset management, featuring real-time data synchronization and localized user experience.
</p>

---

## 🚀 Key Features & Tech Stack

### 🏗️ Architecture & UI
* **ViewBinding:** Safe and efficient interaction with UI components, ensuring null-safety.
* **Navigation Component:** Modern navigation architecture using **NavGraph** and **Bottom Navigation** for seamless screen transitions.
* **Dynamic Lists:** Optimized data rendering using **RecyclerView** with custom adapters.
* **Filtering System:** Integrated **Spinner** components for easy data categorization and filtering.

### ☁️ Backend & Data Management
* **Firebase Authentication:** Secure user sign-up, login, and session management.
* **Cloud Firestore:** Real-time NoSQL database for handling task and asset data syncing across devices.
* **Glide:** High-performance image loading and caching for asset thumbnails and user profiles.
* **Gson:** Efficient JSON serialization and deserialization for data handling and API interactions.

### 🌍 Localization
* **Multilanguage Support:** Full internationalization (i18n) support, allowing the app to scale across different regions and languages (e.g., Az, En).

---

### 🔐 Authentication Flow

The application provides a secure and user-friendly authentication system powered by **Firebase Auth**.

#### **1. Sign In Screen**
The entry point for registered users, focusing on simplicity and security.
* **User Credentials:** Dual input fields for Email and Password.
* **Password Recovery:** A "Forgot Password" feature that triggers a reset email to the user's registered Gmail address via Firebase.
* **Easy Navigation:** Direct link to the Sign Up screen for new users.

#### **2. Sign Up Screen**
A comprehensive registration form designed to capture essential user details.
* **Data Inputs:** Four-field registration including **Email**, **Username**, **Password**, and **Confirm Password**.
* **Validation:** Implementation of "Confirm Password" to prevent entry errors during account creation.
* **Integrated Redirection:** Includes a "Do you have an account? Sign In" prompt for existing users.

---

### 🎨 Visuals

| Sign In Screen | Sign Up Screen |
| :---: | :---: |
| <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/signIn.png" width="250"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/signup.jpeg" width="250"> |
| *Secure Login & Reset Options* | *User Registration & Validation* |

---

### 📋 Task Management System

A dynamic and role-based task tracking system with real-time updates and automated status monitoring.

#### **1. Tasks Dashboard (Role-Based)**
* **Admin View:** Admins can oversee all tasks across the organization. Includes a **Floating Action Button (+)** to assign new tasks to specific users.
* **User View:** A personalized view where users can only see and manage tasks assigned to them.
* **Task Interaction:**
    * **User Action:** Clicking a task opens a dialog with **RadioButtons** to update the status (e.g., In Progress, Done).
    * **Admin Action:** Clicking a task redirects to the **Edit Task** screen for modifications or deletion.

#### **2. Intelligent Status & Visual Feedback**
The `RecyclerView` items dynamically change color based on the task's deadline and progress:
* 🔵 **Blue:** New tasks.
* 🟣 **Purple:** Tasks currently "In Progress".
* 🟡 **Yellow:** High priority — less than **3 days** remaining until deadline.
* 🔴 **Red:** "Overdue" tasks (automatically updated when the deadline passes).
* 🟢 **Green:** Successfully "Completed" tasks.

#### **3. Task Logs & Lifecycle**
* **Automated Logging:** Once a task is marked as **Done** or becomes **Overdue**, it is moved to the **Task Log** screen.
* **Permissions:** Only Admins have the authority to delete tasks from the main list or the logs.
* **Real-time Notifications:** Users receive instant notifications whenever an Admin updates their task status.

#### **4. Gestures & Quick Actions**
* **Swipe-to-Delete:** Admins can quickly remove tasks by **swiping left** on any item. This is implemented using `ItemTouchHelper`, providing a smooth and native user experience.

---

### 🎨 Visuals & Interface

#### **1. Dashboards & Task Creation**
| Admin Task List | User Task List | Add New Task (Admin) |
| :---: | :---: | :---: |
| <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/Tasks_admin.jpeg" width="250"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/tasks_user.jpg" width="250"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/addnewtask.jpeg" width="250"> |
| *Full oversight with (+) Action* | *Personalized assignments* | *Assigning tasks to users* |

#### **2. Task Details & Interaction**
| Admin Task Deatils | User Task Details | Task Logs |
| :---: | :---: | :---: |
| <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/admin_taskdetails.jpg" width="250"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/taskdetailsuser.jpeg" width="250"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/TaskLog.jpeg" width="250"> |
| *Full editing & deletion rights* | *Status update via RadioButtons* | *History of finished/overdue tasks* |

---

### 📦 Inventory & Asset Management

A comprehensive system to track warehouse assets with a lifecycle management workflow from stock to archive.

#### **1. Inventory Dashboard**
* **Real-time Asset Tracking:** Monitor stock items with color-coded statuses:
    * 🟢 **Green:** "New" (In-stock).
    * 🟡 **Yellow:** "Used" assets (In-use/Pre-owned).
    * 🔴 **Red:** "Out of Order" assets.
* **Detailed Insights:** Clicking an asset opens a **Detail Dialog** showing:
    * Visual sample (Image), Brand, Model, Category, Quantity, Receiver Information, and Arrival Date.
* **Smart Archiving:** Assets can be moved from the warehouse to the **Archive** by **swiping left**.
    * *Note:* Assets only disappear from the main inventory if they are no longer in the warehouse.

#### **2. Archive & Deletion Logic**
* **Two-Step Deletion:** To prevent accidental data loss, assets can only be permanently deleted after they have been moved to the **Archive**.
* **Swipe Actions:** A second **left-swipe** within the Archive screen permanently removes the asset from the system.

#### **3. Inventory Log (Immutable Audit Trail)**
* **Automated Logging:** Every single change made to an asset (edits, status updates, movements) is automatically recorded.
* **Data Integrity:** The **Inventory Log** is strictly read-only and immutable; logs cannot be deleted, ensuring a transparent history of all warehouse activities.

---

### 🎨 Visuals & Inventory Interface

#### **Asset Lifecycle & Logs**
| Inventory List | Inventory Archive | Asset Detail Dialog | Edit Asset Screen | Inventory Log |
| :---: | :---: | :---: | :---: | :---: |
| <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/Inventory.jpeg" width="200"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/Inventory.jpeg" width="200"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/Editinventoryitemdetails.jpeg" width="200"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/Editinventoryitem.jpeg" width="200"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/ArchiveLog.jpeg" width="200"> |
| *Status-based color coding* | *See archived assets* | *Complete asset metadata* | *Updating asset info* | *Immutable audit history* |

---

### 🔍 Advanced Filtering System

The app includes a powerful filtering mechanism to help users and admins navigate through large datasets efficiently using dynamic selection.

#### **1. Task Filters**
Tailored views based on the user's role:
* **Admin View:**
    * **All Tasks:** Oversight of every task in the system.
    * **My Tasks:** Tasks specifically assigned to the admin.
    * **By User:** Filter tasks assigned to a specific team member.
    * **By Deadline:** Sort tasks based on urgency and upcoming due dates.
* **User View:**
    * **My Tasks:** View only personally assigned tasks.
    * **By Deadline:** Priority-based sorting to focus on immediate requirements.

#### **2. Inventory Filters**
Uniform filtering for all users to maintain warehouse organization:
* **All Items:** The complete list of assets in the warehouse.
* **My Items:** Assets received or managed by the current user.
* **By User:** Filter assets by the person who received or is responsible for them.
* **By Arrival Date:** Chronological sorting to track stock age and intake history.

---

### 🎨 Filter Interface

| Task Filtering User | Task Filtering Admin | Inventory Filtering |
| :---: | :---: | :---: |
| <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/filter_task_user.jpg" width="350"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/filter_task_admin.jpg" width="350"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/filter.jpeg" width="350"> |
| *Sorting options for user* | *Sorting options for admin* | *Asset tracking by date and user* |

---

### ⚙️ Settings & Configuration

The Settings module provides a personalized experience with a role-based menu structure, ensuring that management tools are only accessible to authorized users.

#### **User View**
* **Account:** Manage and view personal profile credentials.
* **Language Support:** Dynamic multi-language toggle to switch the entire app interface.
* **Sign Out:** Securely terminate the session using Firebase Auth.

#### **Admin View (Enhanced Control)**
Admins have access to all user features, plus a powerful administrative tool:
* **User Management:** A dedicated section where Admins can oversee, manage, and control all registered users within the application.
* **Full Access:** Includes Account, Language, and Sign Out options.

---

### 🎨 Visuals

| Settings (User) | Settings (Admin) |
| :---: | :---: |
| <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/settings_user.jpg" width="250"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/settings_admin.jpeg" width="250"> |
| *Standard preferences* | *Access to Admin Tools* |

---

### 👤 Account & Profile Management

The Account screen allows users to manage their identity and view their system permissions.

* **Profile Details:** Displays **User ID**, **Username**, **Email**, and assigned **Role** (Staff, Admin, or Superadmin).
* **Profile Update:** Users can dynamically update their **Username** directly from this screen via the "Update Name" feature.
* **Role Visibility:**
    * **Staff:** Can view their own profile and basic settings.
    * **Admin:** Can manage staff members but cannot see other admins in the management list.
    * **Superadmin:** Has total oversight, including the ability to see and modify roles for both Staff and other Admins.

---

### 👥 User Management & Admin Controls (Admin/Superadmin Only)

A powerful administrative module for managing the organization's workforce.

* **User List:** Admins can view a list of all staff members.
* **User Details Dialog:** Clicking on a user opens a detailed view with their full information.
* **Role Modification:** Admins/Superadmins can promote or demote users by changing their roles directly from the details dialog.
* **Hierarchical Security:** Superadmins possess elevated privileges to manage the entire user base, including other administrators.

---

### 🌐 Localization & Session

* **Language Settings:** Full support for **Azerbaijani** and **English**, allowing users to switch the interface language instantly.
* **Secure Logout:** The Sign Out feature ensures users can safely terminate their session, clearing all sensitive authentication data via Firebase.

---

### 🎨 Visuals

| Account Profile | User Management (Admin) | User Details & Roles | Language Selection |
| :---: | :---: | :---: | :---: |
| <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/Account.jpeg" width="200"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/usermanagement.jpeg" width="200"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/user_details.jpeg" width="200"> | <img src="https://github.com/Ziyadxan06/TaskManager-AssetManagement-App/blob/main/screenshots/language.jpeg" width="200"> |
| *Personal info & Role* | *Staff list for Admins* | *Modify user permissions

---
