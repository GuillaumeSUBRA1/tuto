# Ajouter Google à votre application Flutter

## 1) Placez votre ```google-services.json``` dans votre projet: 
```
android/app/src/debug/google-services.json     ← debug local
android/app/src/release/google-services.json   ← production signée
```

## 2) Configurez votre projet

### 2.1) Ajoutez dans : 

```
buildscript {
  dependencies {
    classpath 'com.google.gms:google-services:4.3.15'
  }
}
```

### 2.2) Ajoutez dans ```android/app/build.gradle``` : 

```
apply plugin: 'com.google.gms.google-services'
```
et
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