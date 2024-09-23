# Firebase Firestore CRUD Example (Node.js)

This repository demonstrates how to integrate Firebase Firestore with a Node.js application using the Firebase SDK. It includes examples of basic CRUD operations (Create, Read, Update, Delete) on a Firestore database.

## Features
- **Firebase Initialization**: Set up Firebase in a Node.js environment using Firebase SDK.
- **Firestore Integration**: Connect to Firestore and interact with your Firestore database.
- **CRUD Operations**:
  - **Create**: Add new documents to a Firestore collection.
  - **Read**: Fetch all documents from a Firestore collection.
  - **Update**: Modify existing documents in a Firestore collection.
  - **Delete**: (Optional) Remove documents from Firestore.
- **Firestore Security Rules**: Guidelines to set Firestore security rules for testing and production.

## Setup Instructions

### 1. Install Dependencies
Make sure to install the required dependencies by running the following command:

```bash
npm install
```
### 2. Firebase Configuration
Add your Firebase project configuration in the firebaseConfig object located in the main file (e.g., app.js or similar). You can obtain this configuration from your Firebase Console.
