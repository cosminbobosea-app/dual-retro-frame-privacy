# Privacy Policy — Dual Retro Frame Camera

**Effective Date:** November 23, 2026  
**Last Updated:** November 23, 2026  
**Canonical Policy URL:** https://cosminbobosea-app.github.io/dual-retro-frame-privacy/  
**Developer & Support Contact:** cosminbobosea@gmail.com

---

## 1. Overview & Zero Data Collection Commitment

**Dual Retro Frame Camera** (`com.cosminbobosea.dualretroframecamera`) is a 100% offline, local-first photography and videography application for Android.

- **100% Offline & On-Device Media Processing:** The application does not request `android.permission.INTERNET` and performs zero network communication. All camera viewfinder streams, simultaneous Picture-in-Picture (PiP) dual-camera captures, 16-bit RAW (`.dng`) + `.jpg` image pairs, photobooth strips, and `.mp4` videos are processed strictly in local device memory and saved directly to your device's local `MediaStore` (`DCIM/Camera` and `Pictures/DualRetroFrame`).
- **Zero Developer Servers or Cloud Uploads:** We do not operate any backend servers, external API calls, user accounts, or cloud storage. Your photos, videos, audio recordings, location coordinates, and personal files never leave your device unless you explicitly share or open them in an external application.
- **Zero Analytics, Tracking, or Advertising SDKs:** The application contains no third-party analytics SDKs, no crash-reporting telemetry services, no advertising identifiers, and no user profiling tools.

---

## 2. Permissions & How They Are Used Locally

### 2.1 Camera (`android.permission.CAMERA`)
- **Purpose:** Required to render the live camera viewfinder, stream simultaneous front and rear cameras in Dual Camera PiP mode, capture 16-bit RAW (`.dng`) and `.jpg` photos, and record `.mp4` videos.
- **Handling:** Camera frames are processed in real time on your device and written only to local device storage when you trigger the shutter.

### 2.2 Microphone (`android.permission.RECORD_AUDIO`)
- **Purpose:** Used exclusively to record audio tracks during video capture and, only when explicitly toggled on by the user in the viewfinder, to detect on-device voice shutter trigger words (such as *"cheese"* or *"shoot"*).
- **Handling:** Voice shutter detection runs ephemerally in local memory and is never recorded or transmitted. If microphone permission is denied, you can still capture photos and record muted video.

### 2.3 Location (`android.permission.ACCESS_FINE_LOCATION` & `android.permission.ACCESS_COARSE_LOCATION`)
- **Purpose:** Processed strictly locally on-device (with zero network transmission) for two optional, user-controlled photography features:
  1. **Offline Golden Hour & Blue Hour Solar Engine:** Computes real-time astronomical sun azimuth, elevation, and twilight alarms locally on your device using offline solar position mathematics.
  2. **Optional GPS Postcard & EXIF Stamp:** When enabled by the user, embeds GPS coordinates into saved photo metadata or prints user-toggled GPS/city stamps on retro frames.

### 2.4 Photos & Videos (`READ_MEDIA_IMAGES`, `READ_MEDIA_VIDEO`, `READ_MEDIA_VISUAL_USER_SELECTED`, and legacy `READ_EXTERNAL_STORAGE` / `WRITE_EXTERNAL_STORAGE`)
- **Purpose:** Allows the camera to save captured photos, synchronized 16-bit RAW (`.dng`) + `.jpg` pairs, photobooth strips, and `.mp4` videos to `DCIM/Camera` and `Pictures/DualRetroFrame`, display your recent captures in the in-app viewfinder gallery hub, and load user-selected media into the built-in Retro Studio and Video Editor.
- **Handling:** Supports Android 14+ Partial Photo Access (`READ_MEDIA_VISUAL_USER_SELECTED`). The application never scans, indexes, or transmits your media library outside your device.

### 2.5 Notifications, Alarms & Sensors (`POST_NOTIFICATIONS`, `RECEIVE_BOOT_COMPLETED`, `HIGH_SAMPLING_RATE_SENSORS`, `VIBRATE`, `WAKE_LOCK`)
- **Purpose:**
  - `POST_NOTIFICATIONS` and `RECEIVE_BOOT_COMPLETED` are used strictly to schedule and deliver local Golden Hour and Blue Hour photographic alerts when enabled by the user in Golden Hour Settings.
  - `HIGH_SAMPLING_RATE_SENSORS` reads the on-device gyroscope and accelerometer for the 3D electronic horizon level (`0°`) and solar azimuth compass alignment.
  - `VIBRATE` provides tactile shutter and focus confirmation; `WAKE_LOCK` prevents the screen from sleeping while the camera viewfinder is open.

---

## 3. User-Initiated External Editor Handoff

When you tap **EDIT RAW** or select an installed photo editor in the RAW + JPG Gallery Hub, the application uses standard Android intents (`Intent.ACTION_EDIT` / `Intent.ACTION_SEND`) with temporary read URI permissions (`FLAG_GRANT_READ_URI_PERMISSION`) to hand off your selected `.dng` or `.jpg` file to the external editing app you chose. This handoff occurs strictly upon your explicit action; once opened in a third-party app, that application's own privacy policy governs its processing of the file.

---

## 4. Data Retention & Deletion

All application preferences (such as active shooting mode, custom filter presets, and Golden Hour alarm toggles) are stored locally in Android `SharedPreferences` on your device. You can reset all settings at any time inside the app or clear them via **Android Settings → Apps → Dual Retro Frame Camera → Storage → Clear Data**. Captured photos and videos remain in your device's gallery (`DCIM/Camera` and `Pictures/DualRetroFrame`) under your sole control until you delete them.

---

## 5. Children's Privacy

Dual Retro Frame Camera does not knowingly collect, solicit, or store personal information from anyone, including children under the age of 13.

---

## 6. Changes to This Privacy Policy

Any updates to this Privacy Policy will be published at `https://cosminbobosea-app.github.io/dual-retro-frame-privacy/` with an updated revision date.

---

## 7. Contact Us

If you have any questions, privacy inquiries, or feedback regarding Dual Retro Frame Camera, please contact:

- **Email:** cosminbobosea@gmail.com
