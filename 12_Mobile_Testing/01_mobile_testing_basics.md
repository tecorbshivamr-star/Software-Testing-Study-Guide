# Mobile Testing Basics

Testing mobile applications requires validating unique parameters like screen orientation, network switching, battery health, and platform-specific UI interactions.

---

## 3 Mobile Application Architectures

### 1. Native Mobile Apps
Built specifically for a single mobile OS using platform languages (Swift/Objective-C for iOS, Kotlin/Java for Android).
- **Pros:** Maximum performance, full access to device hardware (GPS, camera, sensors).
- **Cons:** High development cost (two separate codebases).

---

### 2. Mobile Web Apps
Websites optimized for mobile browsers. They do not reside on the device; users access them via URL.
- **Pros:** Instant deployments, single codebase.
- **Cons:** Zero hardware access, completely dependent on network stability.

---

### 3. Hybrid Mobile Apps
A wrapper container (like Cordova, Capacitor, or Ionic) hosting a standard web application inside a native shell.
- **Pros:** Code once, run on both platform stores.
- **Cons:** Lower performance, complicated hardware integrations.

---

## Core Mobile Specific Testing Parameters

- **Interruption Testing:** How does the app handle sudden alerts? (Incoming calls, text alerts, low battery warnings, chargers being connected).
- **Screen Rotations:** Smooth transitions between Portrait and Landscape views without crashing or data loss.
- **Network Profiling:** Transitioning from Wi-Fi to 4G/5G, and losing connection entirely (offline mode check).
- **Store Guidelines:** Adherence to Apple App Store or Google Play Store deployment policies.

---

## 📌 Key Takeaways
- Always verify the **offline mode** behaviors of mobile apps.
- Native applications require extensive regression tests since users must manually update store versions.
- Test app behavior during **low memory/battery** conditions.
- Related: [Appium Setup Guide](./02_appium_setup_guide.md).
