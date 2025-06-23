# Ajouter les services google à une application flutter

## 1) Générez une clé SHA-1

### Pour une clé debug :

```keytool -list -v -alias androiddebugkey -keystore ~/.android/debug.keystore -storepass android -keypass android```

### Pour une clé release :

```keytool -list -v -keystore /chemin/vers/keystore.jks -alias ton_alias```

## 2) Créez un projet dans la console google

### 2.1 ) Connectez vous à la console google cloud : [cloud.google.com](https://cloud.google.com/?_gl=1*jt8grf*_up*MQ..&gclid=CjwKCAjw6s7CBhACEiwAuHQckl2f6vrpUm2Tv01WKUuvgy8XKSWLqyLmp1FtuaWksJ5mscdhywUNDRoCcsEQAvD_BwE&gclsrc=aw.ds)

### 2.2) Allez dans la console : [console](https://console.cloud.google.com/)

### 2.3) Créez votre projet

2.3.1) Cliquez sur ```Sélectionnez un projet``` en haut à gauche

2.3.2) Si votre projet existe déjà, sélectionnez le. Sinon, créez-le en cliquant sur ```Nouveau projet``` en haut à droite de la fénêtre.

Note : une fois votre projet créé ou sélectionné, vous pourrez voir ```vous travaillez dans nom_du_projet```

2.3.3) Liez votre projet à Firebase

- 1) Connectez vous à [Firebase](https://console.firebase.google.com)
- 2) Quand vous êtes connecté, cliquez sur ```créez un projet```
- 3) N'ajoutez pas de nom de projet, cliquez sur ```Ajouter Firebase au projet Google Cloud```
- 4) Sélectionnez votre projet
- 5) Suivez les dernières étapes
- 6) Une fois votre projet créé sur Firebase, vous aurez accès à votre vue d'ensemble du projet. Cliquez sur ```Ajouter une application ```, puis sélectionnez votre système d'exploitation (ici android ou ios)
- 7) Ajoutez le nom du package de votre application
- 8) Ajoutez la clé SHA-1 générée dans la [partie 1](#1-générez-une-clé-sha-1) (optionnel)
- 9) Cliquez sur ```Enregistrer l'application```
    - Note : Vous pourrez également ajouter la clé SHA-1 après avoir créé votre projet. Allez dans les paramètres du projet, descendez à la section ```Vos applications```, sélectionnez votre application et cliquez sur ```Ajouter une empreinte```

2.3.4) Téléchargez le google-services.json

- 1) Cliquez sur ```Télécharger google-services.json```. Vous pourrez également télécharger le fichier dans les paramètres du projet, dans la section ```Vos applications```

- 2) Placez votre ```google-services.json``` dans votre projet : 
    -  [FLutter](apps/flutter.md)

## 3) Activer les services

### 3.1) Dans la [console Firebase](```console.firebase.google.com```) :

- Authentication → Google, email/mdp, etc.
- Firestore / Realtime Database
- App Check, Analytics, etc.

### 3.2) Dans la  [console Google cloud](```console.cloud.google.com```) :
- 1) Cliquez sur ```API et Services```
- 2) Allez dans ```Bibliothèque```
- 3) Activez les services dont vous avez besoin
    - Google Calendar API pour le calendrier
    - Google People API pour récupérer les infos utilisateur
    - Google Identity Services pour la connexion

## 4) Créer les identifiants OAuth 2.0 (Google Sign-in)

### 4.1) Dans la  [console Google cloud](```console.cloud.google.com```) :

- 1) Cliquez sur ```API et Services```
- 2) Allez dans ```Identifiants```
- 3) Cliquez sur ```Créer des identifiants```
- 4) Choisissez votre système d'exploitation
- 5) Ajoutez le nom du package et la clé SHA-1 créée [partie 1](#1-générez-une-clé-sha-1)
- 6) Cliquez sur créer


# (Optionnel) Ajoutez des testeurs

### Pour ajouter des utilisateurs test, allez dans la [console Google cloud](```console.cloud.google.com```) : 
- 1) Cliquez sur ```API et Services```
- 2) Allez dans ```Ecran de consentement```
- 3) Allez dans ```Audience```
- 4) Dans la section ```Utilisateurs tests```, cliquez sur ```Add user``` et ajoutez un utilisateur acvec son email google
