# 🏘️ Grama Suvidha Portal
### Digital Village Development Portal — Android App

**Student:** Pavithra M | USN: 1VI22EC116 | VTU | MindMatrix Explorers G4  
**Domain:** Android App Development using GenAI  
**Project:** #79 — Grama Suvidha Portal

---

## 📱 App Overview

Grama Suvidha is a transparency-driven Android application that displays and monitors rural infrastructure projects in Panchayats. Citizens can track project progress, view budgets, and give feedback.

### ✅ Features Implemented
- **Project Dashboard** — RecyclerView with CardViews showing all projects
- **Progress Tracker** — Custom animated progress bars per project
- **Citizen Feedback** — Star ratings (1–5) + Issue reporting system
- **Multi-Language** — Full English ↔ Kannada toggle
- **Offline Support** — JSON data loaded from local assets
- **Before/After Images** — Glide-powered image loading
- **Category Filter** — Filter by Road, Water, Drainage, etc.
- **Search** — Live search by title or location
- **Stats Header** — Total / Completed / In Progress counts

---

## 🗂️ Project Structure

```
GramaSuvidha/
├── app/
│   ├── src/main/
│   │   ├── java/com/gramasuvidha/app/
│   │   │   ├── ui/
│   │   │   │   ├── SplashActivity.java         ← Animated splash screen
│   │   │   │   ├── MainActivity.java           ← Dashboard + Filter + Search
│   │   │   │   ├── detail/
│   │   │   │   │   └── ProjectDetailActivity.java ← Full project details
│   │   │   │   └── feedback/
│   │   │   │       └── FeedbackActivity.java   ← Rating + Issue report
│   │   │   ├── model/
│   │   │   │   ├── Project.java                ← Data model
│   │   │   │   └── Feedback.java               ← Feedback model
│   │   │   ├── viewmodel/
│   │   │   │   └── ProjectViewModel.java       ← MVVM ViewModel
│   │   │   ├── repository/
│   │   │   │   └── ProjectRepository.java      ← JSON + SharedPrefs data
│   │   │   ├── adapter/
│   │   │   │   └── ProjectAdapter.java         ← RecyclerView adapter
│   │   │   └── utils/
│   │   │       └── LanguageUtils.java          ← Budget formatting, colors
│   │   ├── res/
│   │   │   ├── layout/
│   │   │   │   ├── activity_splash.xml
│   │   │   │   ├── activity_main.xml
│   │   │   │   ├── activity_project_detail.xml
│   │   │   │   ├── activity_feedback.xml
│   │   │   │   └── item_project_card.xml
│   │   │   ├── values/
│   │   │   │   ├── strings.xml      ← English strings
│   │   │   │   ├── colors.xml
│   │   │   │   └── themes.xml
│   │   │   ├── values-kn/
│   │   │   │   └── strings.xml      ← ಕನ್ನಡ strings
│   │   │   └── drawable/            ← Custom shapes and backgrounds
│   │   ├── assets/
│   │   │   └── projects.json        ← 5 mock projects (offline data)
│   │   └── AndroidManifest.xml
│   └── build.gradle
├── build.gradle
├── settings.gradle
└── README.md
```

---

## 🛠️ How to Build & Run

### Prerequisites
| Tool | Version |
|------|---------|
| Android Studio | Hedgehog (2023.1.1) or newer |
| JDK | 8 or higher |
| Android SDK | API 34 (compileSdk) |
| Min Android | API 24 (Android 7.0+) |
| Gradle | 8.0+ |

---

### Step-by-Step Build Instructions

#### Step 1 — Install Android Studio
1. Download from: https://developer.android.com/studio
2. Install with default settings
3. Open Android Studio → Complete SDK setup wizard

#### Step 2 — Open the Project
1. Extract the `GramaSuvidha.zip` file to a folder
2. Open Android Studio
3. Click **"Open"** → Navigate to the `GramaSuvidha` folder
4. Click **OK** — Android Studio will index the project

#### Step 3 — Sync Gradle
1. When prompted, click **"Sync Now"** in the top bar
2. Wait for all dependencies to download (needs internet first time)
3. Verify: No red errors in the **Build** panel at the bottom

#### Step 4 — Set Up Emulator (or Physical Device)

**Option A — Emulator:**
1. Go to **Tools → Device Manager**
2. Click **"Create Device"**
3. Select: Phone → Pixel 4 → Next
4. System Image: Select **API 34 (Android 14)** → Download if needed → Next
5. Click **Finish**

**Option B — Physical Android Phone:**
1. Enable **Developer Options**: Settings → About Phone → Tap "Build Number" 7 times
2. Enable **USB Debugging**: Settings → Developer Options → USB Debugging → ON
3. Connect phone via USB → Allow USB Debugging on phone when prompted

#### Step 5 — Run the App
1. Select your device in the device dropdown (top toolbar)
2. Click the green ▶ **Run** button (Shift+F10)
3. The app will build and install automatically
4. App opens with the Grama Suvidha splash screen

---

### 🔧 Troubleshooting

| Problem | Solution |
|---------|----------|
| Gradle sync fails | Check internet connection; try File → Invalidate Caches |
| SDK not found | SDK Manager → Install Android 14 (API 34) |
| Emulator slow | Enable Hardware Acceleration (HAXM/Hyper-V) |
| Images not loading | Internet permission is in Manifest; check emulator has internet |
| Build error "minSdk" | Ensure device/emulator runs Android 7+ (API 24+) |

---

## 🏗️ Architecture — MVVM Pattern

```
View (Activity/Layout)
        ↕ observes LiveData
ViewModel (ProjectViewModel)
        ↕ calls methods
Repository (ProjectRepository)
        ↕ reads/writes
Data Source (assets/projects.json + SharedPreferences)
```

## 📦 Dependencies Used

| Library | Purpose |
|---------|---------|
| Material Components | Chips, CardView, Buttons |
| RecyclerView | Project list |
| ViewModel + LiveData | MVVM architecture |
| Glide 4.16 | Image loading (project photos) |
| Gson | JSON parsing |
| Navigation Component | Back navigation |

---

## 🌐 Sample Project Data

The app ships with 5 real-world-style projects:
1. **Main Road Repair & Widening** — 65% complete — ₹15L budget
2. **Borewell Installation Ward 3** — ✅ 100% complete — ₹8L budget
3. **Community Hall Construction** — 20% complete — ₹25L budget
4. **Drainage System Upgrade** — 90% complete — ₹12L budget
5. **Lake Rejuvenation Siddapura** — Not started — ₹30L budget

---

## 👨‍💻 Student Info

- **Name:** Pavithra M
- **Email:** pavithrachitti19@gmail.com
- **USN:** 1VI22EC116
- **University:** VTU
- **Batch:** Explorer G4
- **Domain:** Android App Development using GenAI
