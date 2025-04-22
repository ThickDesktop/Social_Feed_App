# Social Feed App

## 🚀 Overview

The **Social Feed App** is a **Flutter**-based mobile application that allows users to interact with a social feed. Features include:

- **User Authentication**: Sign up, log in, and log out with Firebase Authentication.
- **Post Creation**: Users can create posts with text and images.
- **Like Posts**: Users can like and engage with others' posts.
- **Real-Time Feed**: Posts appear in the feed as they're created.

Built with **Firebase** for real-time updates, storage, and authentication.

---

## 🎯 Features

- **User Authentication**: Sign up and log in using Firebase Authentication (Email/Password).
- **Post Creation**: Users can create posts with text and images, stored in **Firestore** and **Firebase Storage**.
- **Like System**: Users can like posts, and the status is updated in real-time.
- **Real-Time Feed**: Posts are fetched and displayed in real-time using **Firestore**'s live sync.
- **Image Upload**: Upload and display images with posts via **Firebase Storage**.

---

## 🛠 Tech Stack

- **Flutter**: Framework for building natively compiled applications for mobile, web, and desktop from a single codebase.
- **Firebase**:
  - **Authentication**: For user management and authentication.
  - **Firestore**: Real-time database for storing and syncing posts.
  - **Firebase Storage**: Used for uploading and storing images associated with posts.
- **Dart**: Programming language used with Flutter.

---

## 🔧 Requirements

Before you start, make sure you have:

1. **Flutter SDK** (latest stable version)
2. **Firebase Project** with **Authentication**, **Firestore**, and **Firebase Storage** enabled.
3. A **device/emulator** to run the app.

---

## ⚡ Setup Instructions

### 1. Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/your-username/social-feed-app.git

2. Install Dependencies

Navigate to the project directory and install dependencies:

cd social-feed-app
flutter pub get

3. Configure Firebase
	•	Go to the Firebase Console and create a new project.
	•	Enable Firebase Authentication, Firestore, and Firebase Storage in your Firebase project.
	•	Add your google-services.json (Android) or GoogleService-Info.plist (iOS) to the respective directories in your project.

4. Update Firebase Rules

Ensure Firestore and Firebase Storage rules are set to allow authenticated users to read and write data:

Firestore Rules:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /posts/{postId} {
      allow read: if true;  // Anyone can read posts
      allow write: if request.auth != null;  // Only authenticated users can write
    }
    match /{document=**} {
      allow read: if request.auth != null;  // Authenticated users can read other documents
      allow write: if false;  // Disallow writes to all other collections
    }
  }
}

Firebase Storage Rules:

service firebase.storage {
  match /b/{bucket}/o {
    match /{allPaths=**} {
      allow read, write: if request.auth != null;  // Authenticated users can read and write
    }
  }
}

5. Run the App

Once Firebase is set up, run the app on your emulator or device:

flutter run



⸻

🖼 Screenshots

Here are some screenshots of the app in action:

signup Screen
<img width="497" alt="Screenshot 2025-04-22 at 9 59 26 PM" src="https://github.com/user-attachments/assets/8a9e5af0-4255-4f22-abbf-ba44cc48c104" />



Feed Screen

⸻

📞 Contact

For any inquiries or questions, please contact me at [gsaketh0710@gmail.com or sakethgudavalli@gmail.com].

⸻

Thank you for checking out this project! 🙌
