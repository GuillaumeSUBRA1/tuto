# Add Google to your FLutter app

## 1) place your ```google-services.json``` in your project: 
```
android/app/src/debug/google-services.json     ← debug local
android/app/src/release/google-services.json   ← signed production
```

## 2) Configure your project

### 2.1) Add in  ``` android/build.gradle``` : 

```
buildscript {
  dependencies {
    classpath 'com.google.gms:google-services:4.3.15'
  }
}
```

### 2.2) Add in ```android/app/build.gradle``` : 

```
apply plugin: 'com.google.gms.google-services'
```
and
```
android {
  ...
  buildTypes {
    debug {
      applicationIdSuffix ".debug"
    }
    release {
      signingConfig signingConfigs.release
    }
  }
}
```