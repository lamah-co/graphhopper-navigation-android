# Lamah GraphHopper Navigation Android

This repository is forked from DroidsOnRoids and updated for Android 16KB page size compatibility.

**Current Version:** `0.4.0`

## Version 0.4.0 Updates
- ✅ Android 16KB page size compatible (Google Play requirement)
- ✅ Updated to SDK 34 (Android 14)
- ✅ Upgraded Mapbox SDK to 11.7.1
- ✅ Java 17 support
- ✅ Modern Gradle 8.4 & AGP 8.1.4

## To use or update this package
- Add `github.properties` file in root folder
- Add username & token:
  ```
  username=lamah
  token=[your_github_token]
  ```
  [Generate token here](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

## Build and Test
```bash
# Clean build
./gradlew clean

# Run tests
./gradlew :navigation-android:test

# Build release AAR
./gradlew :navigation-android:assembleRelease

# Output location:
# navigation-android/build/outputs/aar/navigation-android-release.aar
```

## Publish new version
1. Update version in `build.gradle` under publications (line 81)
2. Build and test (see commands above)
3. Publish: `./gradlew publish`

**Troubleshooting:** If you get `artifact file does not exist` error, rename `navigation-android$version.jar` to `navigation-android.jar`


# Navigation SDK

When your users want to get from one location to another, don’t push them out of your application into a generic map application.
Instead, keep them engaged with your application 100% of the time with in-app turn-by-turn navigation.

The Navigation SDK for Android contains logic needed to get timed navigation instructions.

It plays well with the open source [GraphHopper server](https://github.com/graphhopper/graphhopper/tree/master/navigation) as well as the [GraphHopper Directions API](https://www.graphhopper.com/products/).

## License

[MIT License](./LICENSE)

It is 100% open source and was forked 2018 from Mapbox due to [licensing issues](https://github.com/mapbox/mapbox-navigation-android/issues/1391).

## Getting Started

If you are looking to include this inside your project, please also have a look into the
[Android example](https://github.com/graphhopper/graphhopper-navigation-example).

Add this snippet to your `build.gradle` file to use this SDK:

```gradle
implementation 'com.lamah.graphhopper:navigation-android:0.4.0'
```

**Requirements:**
- minSdkVersion: 21+
- compileSdkVersion: 34+
- Java 17+

## 16KB Page Size Compatibility

This library is **16KB compatible** (no native libraries).

### Verify the Library
```bash
# 1. Build the library
./gradlew :navigation-android:assembleRelease

# 2. Check the AAR for native libraries (.so files)
# Run this from project root:
unzip -l ./navigation-android/build/outputs/aar/navigation-android-release.aar | grep "jni/"

# Empty result = No native libraries = 16KB compatible ✅
```

**What is AAR?** Android Archive file - like a ZIP containing compiled code, resources, and native libraries (if any).

### Verify in Your App
**Easiest Method (Recommended):**
1. Integrate this library in your app
2. Build your app: `./gradlew assembleRelease` or `./gradlew bundleRelease`
3. Upload APK/AAB to Play Console Internal Testing track
4. Google automatically validates 16KB compatibility ✅

**Manual Check:**
```bash
# In your app project
./gradlew assembleRelease

# Check all native libraries in your APK
unzip -l app/build/outputs/apk/release/app-release.apk | grep "\.so$"
```

All native libraries from dependencies must be 16KB aligned. This library has none, so it's compliant.
