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
```javascript
const firebaseConfig = {
  apiKey: "your-apiKey",
  authDomain: "your-authDomain",
  projectId: "your-projectId",
  storageBucket: "your-storageBucket",
  messagingSenderId: "your-messagingSenderId",
  appId: "your-appId"
};
```
### 3. Set Firestore Security Rules
For testing purposes, you can temporarily set your Firestore security rules to allow public access. Go to the Firestore Database > Rules tab and replace the rules with:
Example configuration:

```plaintext
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}

```
Note: This setting is not recommended for production. For production, ensure your rules are properly secured based on user authentication.
### 4. Run the Project
After configuring Firebase and setting up security rules, you can run the Node.js project:
```bash
node app.js
```
## CRUD Operations Overview
### 1. Add a Document
This function adds a new user document to the users collection in Firestore:
```javascript
async function addNewUser() {
  const docRef = await addDoc(collection(db, "users"), {
    name: "John Doe",
    email: "john.doe@example.com",
    age: 30
  });
  console.log("Document written with ID: ", docRef.id);
}
```
### 2. Get All Documents
This function retrieves all documents from the users collection:
```javascript
async function getAllUsers() {
  const querySnapshot = await getDocs(collection(db, "users"));
  querySnapshot.forEach((doc) => {
    console.log(`${doc.id} => ${JSON.stringify(doc.data())}`);
  });
}
```
### 3. Update a Document
This function updates an existing document's age field:
```javascript
async function updateUser(userId) {
  const userDoc = doc(db, "users", userId);
  await updateDoc(userDoc, {
    age: 31
  });
  console.log("Document updated");
}
```
### Technologies Used
- Node.js
- Firebase Firestore
- ES6 Modules

### Requirements
Firebase account and Firestore enabled in your Firebase project.
Firebase SDK configuration.

### License
This project is licensed under the MIT License. Feel free to fork, modify, and contribute as needed.

### Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.
