# Firebase Asynchronous Operation Error

This repository demonstrates a common error in Firebase applications: accessing properties of a document snapshot before the data has been fully populated. This often occurs when using asynchronous operations and attempting to access data before the promise resolves.

## Problem

The `bug.js` file shows code that attempts to access a field from a Firestore document snapshot immediately after initiating the retrieval.  Due to the asynchronous nature of Firestore operations, this leads to the property being undefined, resulting in an error.

## Solution

The `bugSolution.js` file provides a corrected approach. By using `.then()` to handle the promise's resolution, the code ensures that the snapshot's data is available before attempting to access its properties.

## How to Reproduce

1. Clone this repository.
2. Install the required dependencies: `npm install firebase`
3. Configure your Firebase project and set the `apiKey`, `authDomain`, `projectId`, etc., in the `firebase.js` file.
4. Run `bug.js` to observe the error.
5. Run `bugSolution.js` to see the corrected implementation.