# Add google services to a flutter app

## 1) Generate a SHA-1 key

### For a debug key :

```keytool -list -v -alias androiddebugkey -keystore ~/.android/debug.keystore -storepass android -keypass android```

### For a release key :

```keytool -list -v -keystore /chemin/vers/keystore.jks -alias ton_alias```

## 2) Create a projet in google console

### 2.1 ) Connect to google cloud console: [cloud.google.com](https://cloud.google.com/?_gl=1*jt8grf*_up*MQ..&gclid=CjwKCAjw6s7CBhACEiwAuHQckl2f6vrpUm2Tv01WKUuvgy8XKSWLqyLmp1FtuaWksJ5mscdhywUNDRoCcsEQAvD_BwE&gclsrc=aw.ds)

### 2.2) Go to console : [console](https://console.cloud.google.com/)

### 2.3) Create your project 

2.3.1) Clic on ```Select a project``` on top left

2.3.2) If your projet already exists, select it. Otherwise, create it by clicking on ```New project``` on top right of the widow.

Note : When your porjkect is created, you will see ```You're working in name_of_project```

2.3.3) Link your project to Firebase

- 1) Connect to [Firebase](https://console.firebase.google.com)
- 2) When you are connected, clic on ```create a project```
- 3) Donc add a project name, clic on ```Add Firebase to Google Cloud project```
- 4) Select your project
- 5) Follow last steps
- 6) When your project is created on Firebase, you will have acces to your porject ov overview. Clic on ```Add application```, then select your 
operating system (here android or ios)
- 7) Add the package name of your app (ex : ```com.example.app```) 
- 8) Add the key SHA-1 generated in 1st part [1st part](#1-generate-a-sha-1-key) (optionnal)
- 9) Cliquez sur ```Enregistrer l'application```
    - you can add the key SHA-1 after creating your porject. Go to your project settings, go to ```Your apps``` section, select your app and clic on ```Add a print```

2.3.4) Download google-services.json

- 1) Clic on ```Download google-services.json```. You can also download the file in your project settings, in ```Your apps``` section

- 2) place your ```google-services.json``` in your project : 
    -  [FLutter](apps/flutter.md)

## 3) Activate services

### 3.1) In [console Firebase](```console.firebase.google.com```) :

- Authentication → Google, email/mdp, etc.
- Firestore / Realtime Database
- App Check, Analytics, etc.

### 3.2) In  [console Google cloud](```console.cloud.google.com```) :
- 1) Clic on ```API and Services```
- 2) Go to ```Library```
- 3) Activate the services you need
    - Google Calendar API for calendar
    - Google People API to get user infos
    - Google Identity Services for connexion


## 4) Create OAuth 2.0 ids (Google Sign-in)

### 4.1) In  [console Google cloud](```console.cloud.google.com```) :

- 1) Clic on ```API and Services```
- 2) Go to ```Ids```
- 3) Clic on ```Créate ids```
- 4) Choose your operating system
- 5) Add the package name and the SHA-1 key generated in [1st part](#1-generate-a-sha-1-key)
- 6) Clic on create


# (Optionnel) Add test users

### To add test users, go in  [console Google cloud](```console.cloud.google.com```) : 
- 1) Clic on ```API and Services```
- 2) Go to ```Consent screen```
- 3) Go to ```Audience```
- 4) In section ```Test Users```, clic on ```Add user``` and add a user with his google email
