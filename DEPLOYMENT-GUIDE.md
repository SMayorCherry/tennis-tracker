# Tennis Tracker - Android Deployment Guide

## 🚀 Option 1: PWA (Progressive Web App) - EASIEST

### ✅ Already Set Up - Just Host and Install!

**Steps:**
1. **Host the files** (tennis-tracker.html, manifest.json, sw.js)
2. **Open on Android Chrome/Edge**
3. **Menu → "Add to Home Screen"**
4. **App installs like native app!**

**Hosting Options:**
- **GitHub Pages**: Free, automatic HTTPS
- **Netlify**: Free, easy deployment
- **Firebase Hosting**: Free, fast CDN

---

## 📱 Option 2: Cordova - True Native Android App

### Installation:
```bash
npm install -g cordova
cordova create TennisTracker com.yourname.tennistracker "Tennis Tracker"
cd TennisTracker
```

### Setup:
```bash
# Add Android platform
cordova platform add android

# Copy your files to www/ folder
cp ../tennis-tracker.html www/index.html
cp ../manifest.json www/
cp ../sw.js www/

# Configure config.xml (see below)
```

### config.xml Configuration:
```xml
<?xml version='1.0' encoding='utf-8'?>
<widget id="com.yourname.tennistracker" version="1.0.0">
    <name>Tennis Performance Tracker</name>
    <description>Track tennis performance with detailed statistics</description>
    <author email="your@email.com">Your Name</author>
    
    <content src="index.html" />
    <access origin="*" />
    
    <preference name="DisallowOverscroll" value="true" />
    <preference name="android-minSdkVersion" value="22" />
    <preference name="android-targetSdkVersion" value="33" />
    
    <platform name="android">
        <icon density="ldpi" src="res/icon/android/ldpi.png" />
        <icon density="mdpi" src="res/icon/android/mdpi.png" />
        <icon density="hdpi" src="res/icon/android/hdpi.png" />
        <icon density="xhdpi" src="res/icon/android/xhdpi.png" />
    </platform>
</widget>
```

### Build APK:
```bash
# Build for Android
cordova build android

# Build for release
cordova build android --release

# Generated APK location:
# platforms/android/app/build/outputs/apk/debug/app-debug.apk
```

### Install on Device:
```bash
# Enable USB Debugging on phone
# Connect via USB
cordova run android
```

---

## 🔧 Option 3: Android Studio WebView App

### 1. Create New Android Project
- Open Android Studio
- Create "Empty Activity"
- Name: "Tennis Tracker"

### 2. Add Internet Permission (AndroidManifest.xml):
```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### 3. MainActivity.java:
```java
public class MainActivity extends AppCompatActivity {
    private WebView webView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        webView = findViewById(R.id.webview);
        webView.getSettings().setJavaScriptEnabled(true);
        webView.getSettings().setDomStorageEnabled(true);
        webView.setWebViewClient(new WebViewClient());
        
        // Load your hosted app or local file
        webView.loadUrl("file:///android_asset/tennis-tracker.html");
        // OR webView.loadUrl("https://your-hosted-url.com");
    }
}
```

### 4. Add HTML files to assets/
- Copy tennis-tracker.html to app/src/main/assets/

---

## ⚡ Option 4: Capacitor (Modern Alternative)

### Setup:
```bash
npm install @capacitor/core @capacitor/cli
npx cap init "Tennis Tracker" "com.yourname.tennistracker"
npm install @capacitor/android
npx cap add android
```

### Build:
```bash
# Copy web assets
npx cap copy

# Open in Android Studio
npx cap open android
```

---

## 🌟 Recommended Approach: PWA First!

**Why PWA?**
- ✅ **Works immediately** - no complex setup
- ✅ **Automatic updates** - just update your hosted files
- ✅ **Offline capable** - service worker caching
- ✅ **Native-like experience** - full screen, home screen icon
- ✅ **No app store required** - install directly from browser
- ✅ **Cross-platform** - works on iOS too

**When to use Cordova/Native:**
- Need device features (camera, GPS, etc.)
- Want to publish on Google Play Store
- Need advanced native integrations

---

## 📚 Quick Start: PWA Deployment

### 1. Host on GitHub Pages (Free):
```bash
1. Create new GitHub repository
2. Upload all files (tennis-tracker.html, manifest.json, sw.js)
3. Settings → Pages → Source: Deploy from branch
4. Access: https://yourusername.github.io/repo-name/tennis-tracker.html
```

### 2. Install on Android:
```
1. Open URL in Chrome
2. Menu (⋮) → "Add to Home Screen"
3. Tap "Add" 
4. App appears on home screen!
```

### 3. Features Available:
- ✅ Full-screen app experience
- ✅ Works offline after first load
- ✅ Home screen icon
- ✅ Splash screen
- ✅ All tennis tracking features
- ✅ Match history stored locally

---

## 🔧 Troubleshooting

**PWA not showing "Add to Home Screen"?**
- Ensure HTTPS (GitHub Pages provides this)
- Check manifest.json is accessible
- Chrome DevTools → Application → Manifest

**Cordova build errors?**
- Ensure Android SDK is installed
- Check Java/Gradle versions
- Run: `cordova requirements`

**Need help?**
- PWA: Test locally first with `python -m http.server`
- Cordova: Check platform requirements
- Native: Ensure Android Studio setup is complete 