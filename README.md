<p align="center">
  <img src="zokistasks_icon.png" alt="ZokiList Icon" width="150" height="150">
</p>

# ZokiList

## Overview
ZokiList is an iOS application that connects to Firebase to help users organize and manage their tasks across multiple categories. The app provides a simple, clean interface following iOS design guidelines.

## Features
- Device-specific task lists for enhanced privacy and security
- User identification via simple name entry (no formal authentication required)
- Four distinct task categories: Daily Tasks, Sams, Woodman, and Other
- Task creation, editing, and completion tracking
- Task detail view for reviewing and modifying task information
- User profile management with personalized welcome screen
- Secure Keychain storage for persistent user identification across app reinstallations
- Logout functionality with data preservation
- Real-time updates from Firebase database
- Clean, modern UI built with SwiftUI following iOS design principles

## Technical Specifications
- iOS 15.0+ (recommended)
- Swift 5.5+
- Firebase integration via Swift Package Manager
- SwiftUI for the user interface

## Project Structure
```
ZokiList/
├── Models/
│   ├── Task.swift       # Task data model with Firestore integration
│   └── Title.swift      # Title data model
├── Views/
│   ├── TaskCell.swift   # Individual task row view
│   ├── TaskListView.swift # Main list view for tasks
│   ├── TaskDetailView.swift # Detailed view for viewing/editing tasks
│   ├── AddTaskView.swift # View for creating new tasks
│   ├── EditTaskView.swift # View for editing existing tasks
│   ├── WelcomeView.swift # First-time user onboarding
│   ├── UserProfileView.swift # User account management
│   └── MainView.swift # Main app container view
├── Services/
│   ├── FirebaseService.swift # Firebase data fetching service
│   └── UserManager.swift # User session management
├── Utilities/
│   └── KeychainHelper.swift # Secure storage utilities
├── AppDelegate.swift    # App initialization with Firebase setup
├── SceneDelegate.swift  # SwiftUI integration
└── GoogleService-Info.plist # Firebase configuration
```

## Recent Updates
- Implemented device-specific task lists for enhanced privacy and security
- Improved user ID generation to ensure data privacy across different devices
- Implemented secure Keychain storage for persistent user identification
- Added logout functionality with data preservation
- Added four distinct task categories: Daily Tasks, Sams, Woodman, and Other
- Created task detail view for better task management
- Fixed UI issues with task selection and display
- Added loading indicators for improved user experience
- Disabled autocorrection for name input to prevent errors
- Temporarily disabled user switching feature (coming in future update)
- Implemented user-specific task lists with unique user IDs

## Upcoming Features
- Client-side caching for improved performance
- Offline persistence for Firestore
- Enhanced security rules for Firebase
- Re-enabled user switching with proper profile management
- Task sharing options between users
- Custom task categories and sorting options
- Advanced task filtering

## Setup Instructions

### Prerequisites
- Xcode 14.0+
- An active Firebase account
- Firebase project with Firestore database

### Firebase Setup
1. Create a Firebase project at [console.firebase.google.com](https://console.firebase.google.com)
2. Add an iOS app to your Firebase project
3. Download the GoogleService-Info.plist and add it to your project
4. Create the following structure in Firestore:
   - `title` collection with a `main` document containing a `text` string field
   - `users` collection that will contain user-specific documents, each with:
     - A document ID matching the user's unique identifier
     - A `tasks` subcollection with task documents containing:
       - `title` (string)
       - `completed` (boolean)
       - `date` (timestamp)
       - `category` (string - one of "Daily Tasks", "Sams", "Woodman", or "Other")

### Running the Project
1. Open the project in Xcode using the `.xcodeproj` file
2. Make sure all Swift Package Manager dependencies are resolved
3. Build and run the application on a simulator or device

## Firebase Data Structure

### Title Collection
```
title/
└── main/
    └── text: "Today's Tasks" (or any title you prefer)
```

### Tasks Collection
```
tasks/
├── task1/
│   ├── title: "Task name"
│   ├── completed: false
│   └── date: [timestamp]
├── task2/
│   ├── ...
└── ...
```

## Future Enhancements
- User authentication
- Task creation and editing
- Task completion tracking
- Notifications for task reminders
- Dark mode support
- Widget extension

## Troubleshooting
- If you encounter build errors related to Info.plist, ensure that build settings point to the correct path
- For Firebase connection issues, verify that GoogleService-Info.plist is properly added to the project
- If Swift Package Manager dependencies are not resolving, try resetting the package caches in Xcode

## License
This project is intended for personal use and learning purposes.

---

Created by TR, 2025
