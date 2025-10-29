# 🛠️ Android Studio Fixtures

This repository is dedicated to fixing **JDK-related issues** in Android Studio.
> ## CHECK THE LATEST STABLE VERSION OF JDK AND SDK BEFORE IMPLEMENTING

---

## ⚙️ Step 1: Check `android/build.gradle`

Ensure your `build.gradle` file contains the following:

```gradle
buildscript {
    repositories {
        google()
        mavenCentral()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:8.2.1' // 
    }
}
```

> 🔹 If the above section is missing, **add it at the top** of your `android/build.gradle` file.

---

## 📦 Step 2: Update `gradle/wrapper/gradle-wrapper.properties`

Make sure your Gradle distribution is using a **stable version**:

```properties
distributionUrl=https\://services.gradle.org/distributions/gradle-8.10.2-all.zip
```

> ✅ **Version 8.10.2** is a stable release.

---

## 🧩 Step 3: Verify `settings.gradle`

Your `settings.gradle` file should include the following plugin configurations:

```gradle
plugins {
    id "dev.flutter.flutter-plugin-loader" version "1.0.0"
    id "com.android.application" version "8.3.2" apply false
    id "org.jetbrains.kotlin.android" version "2.0.20" apply false
}
```

---

## 📁 Step 4: Edit `app/build.gradle`

Ensure your Android configuration looks like this:

```gradle
android {
    namespace = "com.example.app"
    compileSdk = flutter.compileSdkVersion
    ndkVersion = flutter.ndkVersion

    compileOptions {
        sourceCompatibility = 17
        targetCompatibility = 17
    }

    kotlinOptions {
        jvmTarget = 17
    }
}
```

> 💡 **JDK 17** is the recommended stable version.

---

