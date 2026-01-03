# 🔧 BengkelKu - Vehicle Reparation App

<div align="center">

![Android](https://img.shields.io/badge/Android-3DDC84?logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-1.9.0-7F52FF?logo=kotlin&logoColor=white)
![SDK](https://img.shields.io/badge/SDK-34-brightgreen)
![Navigation](https://img.shields.io/badge/Navigation-2.7.7-blue)
![License](https://img.shields.io/badge/license-MIT-green.svg)

**A vehicle repair service marketplace connecting customers with mechanics (Montir)**

[Features](#-features) • [Screenshots](#-screenshots) • [Installation](#-installation) • [Architecture](#-architecture) • [Contributing](#-contributing)

</div>

---

## 📖 Overview

BengkelKu is a native Android application that connects vehicle owners with professional mechanics (Montir). Customers can browse available mechanics, view their profiles and pricing, chat directly, and request repair services. Mechanics can manage their service rates, communicate with customers, and accept repair requests.

Built with modern Android development practices using Single Activity Architecture, Navigation Component, Safe Args, and Kotlin Parcelize.

## ✨ Features

### 🔐 Authentication

| Feature | Description |
|---------|-------------|
| **Customer Registration** | Register with name, username, and password |
| **Mechanic Registration** | Register with additional details: description, experience, and service price |
| **Secure Login** | Username and password authentication |
| **Role-based Access** | Separate interfaces for Customers and Mechanics |

### 👤 Customer Features

- **🏠 Dashboard** - Personalized welcome screen with mechanic list
- **🔍 Search Mechanics** - Real-time search by mechanic name
- **👨‍🔧 View Mechanic Profiles** - See experience, description, and pricing
- **💬 Direct Chat** - Real-time messaging with mechanics
- **📝 Request Service** - Send repair service requests
- **📋 Chat History** - View all conversation threads

### 🔧 Mechanic (Montir) Features

- **🏠 Dashboard** - View total earnings and customer chats
- **💰 Set Pricing** - Update service rates anytime
- **💬 Customer Chats** - Manage all customer conversations
- **✅ Accept Requests** - Accept or manage repair requests
- **📊 Earnings Tracking** - Monitor total income

### 💬 Chat System

- **Real-time Messaging** - Instant message delivery
- **Conversation History** - Full chat history preservation
- **Request Integration** - Service requests within chat
- **Multi-conversation** - Handle multiple customer/mechanic chats

### 📦 Order Management

| Status | Description |
|--------|-------------|
| **Requested** | Customer sent a repair request |
| **Accepted** | Mechanic accepted the request |

## 📱 Screenshots

| Login | Customer Home | Mechanic Detail |
|:---:|:---:|:---:|
| ![Login](screenshots/login.png) | ![Customer Home](screenshots/customer_home.png) | ![Detail](screenshots/mechanic_detail.png) |

| Customer Chat | Mechanic Home | Mechanic Chat |
|:---:|:---:|:---:|
| ![Customer Chat](screenshots/customer_chat.png) | ![Mechanic Home](screenshots/mechanic_home.png) | ![Mechanic Chat](screenshots/mechanic_chat.png) |

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| [Kotlin](https://kotlinlang.org/) | Primary programming language |
| [Navigation Component](https://developer.android.com/guide/navigation) | Single Activity navigation |
| [Safe Args](https://developer.android.com/guide/navigation/navigation-pass-data#Safe-args) | Type-safe navigation arguments |
| [Kotlin Parcelize](https://developer.android.com/kotlin/parcelize) | Parcelable implementation |
| [View Binding](https://developer.android.com/topic/libraries/view-binding) | Type-safe view access |
| [RecyclerView](https://developer.android.com/guide/topics/ui/layout/recyclerview) | Efficient list display |
| [Material Components](https://material.io/develop/android) | UI components and theming |

## 📋 Requirements

- **Android Studio**: Hedgehog (2023.1.1) or later
- **Minimum SDK**: API 34 (Android 14)
- **Target SDK**: API 34
- **JDK**: 1.8+
- **Gradle**: 8.3.0

## 🚀 Installation

### Clone the Repository

```bash
git clone https://github.com/gechdr/Simple-Vechicle-Reparation-App.git
cd Simple-Vechicle-Reparation-App
```

### Open in Android Studio

1. Launch **Android Studio**
2. Select **File > Open**
3. Navigate to the cloned repository
4. Click **OK** and wait for Gradle sync

### Build and Run

```bash
# Build the project
./gradlew build

# Install on connected device/emulator
./gradlew installDebug
```

Or click the **Run** button (▶️) in Android Studio.

### Demo Accounts

The app comes with pre-configured test accounts:

**Customers:**

| Username | Password | Name |
|----------|----------|------|
| `morgan` | `123` | Christian Morgan |
| `arias` | `123` | Randy Arias |

**Mechanics (Montir):**

| Username | Password | Name | Experience | Price |
|----------|----------|------|------------|-------|
| `charles` | `123` | Charles Medon | 2 years | Rp 50,000 |
| `martin` | `123` | Cole Martin | 3 years | Rp 75,000 |
| `andy` | `123` | Andy Tran | 4 years | Rp 100,000 |
| `esme` | `123` | Esme Watts | 1 year | Rp 25,000 |

## 📁 Project Structure

```
Kotlin-VechicleReparationApp/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/tugasm5_6958/
│   │   │   │   │
│   │   │   │   ├── Activities/
│   │   │   │   │   └── MainActivity.kt              # Single activity host
│   │   │   │   │
│   │   │   │   ├── Fragments/
│   │   │   │   │   ├── LoginFragment.kt             # User login
│   │   │   │   │   ├── RegisterCustomerFragment.kt  # Customer registration
│   │   │   │   │   ├── RegisterMontirFragment.kt    # Mechanic registration
│   │   │   │   │   ├── HomeCustomerFragment.kt      # Customer dashboard
│   │   │   │   │   ├── HomeMontirFragment.kt        # Mechanic dashboard
│   │   │   │   │   ├── DetailMontirFragment.kt      # Mechanic profile view
│   │   │   │   │   ├── CustomerChatFragment.kt      # Customer chat screen
│   │   │   │   │   ├── MontirChatFragment.kt        # Mechanic chat screen
│   │   │   │   │   ├── CustomerHomeChatFragment.kt  # Customer chat list
│   │   │   │   │   └── MontirHomeChatFragment.kt    # Mechanic chat list
│   │   │   │   │
│   │   │   │   ├── Adapters/
│   │   │   │   │   ├── MontirAdapter.kt             # Mechanic list adapter
│   │   │   │   │   ├── ChatAdapter.kt               # Chat messages adapter
│   │   │   │   │   ├── HomeChatCustomerAdapter.kt   # Customer chat list adapter
│   │   │   │   │   └── HomeChatMontirAdapter.kt     # Mechanic chat list adapter
│   │   │   │   │
│   │   │   │   ├── Models/
│   │   │   │   │   ├── User.kt                      # User data class
│   │   │   │   │   ├── Chat.kt                      # Chat message data class
│   │   │   │   │   └── Order.kt                     # Service order data class
│   │   │   │   │
│   │   │   │   ├── Utils/
│   │   │   │   │   └── CurrencyUtils.kt             # Rupiah formatting
│   │   │   │   │
│   │   │   │   └── Data/
│   │   │   │       └── MockDB.kt                    # In-memory database
│   │   │   │
│   │   │   ├── res/
│   │   │   │   ├── layout/                          # Fragment layouts
│   │   │   │   ├── navigation/
│   │   │   │   │   └── nav_graph.xml                # Navigation graph
│   │   │   │   ├── menu/                            # Menu resources
│   │   │   │   └── values/                          # Colors, strings, themes
│   │   │   │
│   │   │   └── AndroidManifest.xml
│   │   │
│   │   └── test/                                    # Unit tests
│   │
│   └── build.gradle.kts
│
├── gradle/
│   └── libs.versions.toml
│
└── README.md
```

## 🏗️ Architecture

### Single Activity Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                      MainActivity                            │
│                  (NavHostFragment)                           │
└──────────────────────────┬──────────────────────────────────┘
                           │
         ┌─────────────────┼─────────────────┐
         │                 │                 │
         ▼                 ▼                 ▼
┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   Login     │    │  Register   │    │  Register   │
│  Fragment   │    │  Customer   │    │   Montir    │
└──────┬──────┘    └─────────────┘    └─────────────┘
       │
       ├─────────────────────────────────┐
       │                                 │
       ▼                                 ▼
┌─────────────────┐              ┌─────────────────┐
│    Customer     │              │     Montir      │
│      Home       │              │      Home       │
└────────┬────────┘              └────────┬────────┘
         │                                │
    ┌────┴────┐                     ┌─────┴─────┐
    ▼         ▼                     ▼           ▼
┌───────┐ ┌───────┐             ┌───────┐   ┌───────┐
│Detail │ │ Chat  │             │ Chat  │   │ Chat  │
│Montir │ │ List  │             │ List  │   │ Room  │
└───┬───┘ └───┬───┘             └───────┘   └───────┘
    │         │
    ▼         ▼
┌─────────────────┐
│   Chat Room     │
└─────────────────┘
```

### Navigation Graph

```xml
LoginFragment
    ├── → RegisterCustomerFragment
    ├── → RegisterMontirFragment
    ├── → HomeCustomerFragment
    │       ├── → DetailMontirFragment
    │       │       └── → CustomerChatFragment
    │       └── → CustomerHomeChatFragment
    │               └── → CustomerChatFragment
    └── → HomeMontirFragment
            └── → MontirChatFragment
```

### Data Models

#### User
```kotlin
@Parcelize
data class User(
    val name: String,
    val username: String,
    val password: String,
    val role: String,              // "Customer" or "Montir"
    val description: String?,      // Mechanic only
    val lengthOfEmployment: String?, // Mechanic only
    var price: Int?,               // Mechanic service rate
    var pendapatan: Int?           // Mechanic total earnings
): Parcelable
```

#### Chat
```kotlin
@Parcelize
data class Chat(
    val id: Int,
    val sender: String,
    val receiver: String,
    val message: String
): Parcelable
```

#### Order
```kotlin
@Parcelize
data class Order(
    val id: Int,
    val customer: String,
    val montir: String,
    var status: String    // "Requested", "Accepted"
): Parcelable
```

## 📝 Usage Guide

### For Customers

1. **Login/Register** - Create an account or login with existing credentials
2. **Browse Mechanics** - View available mechanics on home screen
3. **Search** - Use search bar to find specific mechanics by name
4. **View Profile** - Tap a mechanic to see their full profile
5. **Start Chat** - Initiate conversation with chosen mechanic
6. **Request Service** - Send a repair service request
7. **Manage Chats** - Access all conversations from chat button

### For Mechanics

1. **Login/Register** - Create mechanic account with experience and pricing
2. **View Dashboard** - See total earnings and customer chats
3. **Update Pricing** - Modify service rates and save
4. **Respond to Chats** - Reply to customer inquiries
5. **Accept Requests** - Accept incoming repair requests
6. **Track Earnings** - Monitor total income from services

## 🔧 Configuration

### Adding More Vehicle Types

Extend the `User` model and UI to support vehicle specializations:

```kotlin
data class User(
    // ... existing fields
    val specializations: List<String>? // e.g., ["Car", "Motorcycle", "Truck"]
)
```

### Implementing Real Database

Replace `MockDB.kt` with Room Database:

```kotlin
// 1. Add Room dependencies
implementation("androidx.room:room-runtime:2.6.1")
kapt("androidx.room:room-compiler:2.6.1")

// 2. Create Entity classes with @Entity annotation
// 3. Create DAO interfaces
// 4. Update MockDB functions to use Room queries
```

### Adding Push Notifications

Integrate Firebase Cloud Messaging for real-time chat notifications.

## 🧪 Testing

### Run Unit Tests

```bash
./gradlew test
```

### Run Instrumented Tests

```bash
./gradlew connectedAndroidTest
```

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### Feature Ideas

- [ ] Push notifications for new messages
- [ ] Image sharing in chat
- [ ] Location-based mechanic search
- [ ] Rating and review system
- [ ] Payment integration
- [ ] Appointment scheduling
- [ ] Service history tracking
- [ ] Vehicle management (multiple vehicles per customer)
- [ ] Mechanic availability status
- [ ] Price negotiation in chat
- [ ] Service categories (engine, body, electrical, etc.)
- [ ] Emergency roadside assistance
- [ ] Firebase backend integration

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software...
```

## 🙏 Acknowledgments

- [Android Developers](https://developer.android.com/) - Official documentation
- [Material Design](https://material.io/) - Design guidelines
- [Kotlin](https://kotlinlang.org/) - Programming language
- [Navigation Component](https://developer.android.com/guide/navigation) - Navigation architecture

---

<div align="center">

**Built with Kotlin**

[🔝 Back to Top](#-bengkelku---vehicle-reparation-app)

</div>
