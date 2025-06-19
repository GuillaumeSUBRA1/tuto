# Déployer un projet angular sur github

### 1) Créez une branche ```gh-pages``` /// Create a ```gh-pages``` branch

```
git checkout -b gh-pages
```

### 2) Ajoutez la branche au repository /// Add the branch to repository

```
git push origin gh-pages
```

### 3) Retournez sur la branche ```main``` /// Return on ```main``` branch

```
git checkout main
```

### 4) Installez la dépendance angular /// Install angular dependency 

```
nd add angular-cli-ghpages
```

### 5) Créez le dossier ```dist``` qui contiendra le code de votre projet en production /// Create the folder ```dist``` which will contain the code of your project in production 

```
ng build --configuration production --base-href=https://{{nom_de_domaine}}/{{nom_du_projet}}/
```
#### Note : n'oubliez pas le dernier ```/``` à la fin du lien /// don't forget the last ```/``` at the end of link

### 6) Faîtes un commit du dossier ```dist``` sur la branche gh-pages et lancez le déploiement /// Commit the folder ```dist``` on the branch ```gh-pages``` and launch deployment

```
npx angular-cli-ghpages --dir=dist/{{nom_du_dossier}}
```
#### Note : Le chemin passé en argument de ```--dir``` soit contenir un fichier ```index.html```. Si l'étape 5 a créé un dossier ```browser``` qui contient ce fichier, ajoutez le au chemin. /// The folder passed in argument of ```--dir``` must contain a file ```index.html```. If step 5 created a folder ```browser``` which contains the file, add it to path.

### 7) Rendez-vous sur votre repository sur github. Allez dans l'onglet ```Settings```, puis dans ```Pages``` dans le menu latéral. Vous trouverez un encadré qui indique "Your site is live at {{lien_du_site}}". Cliquez sur le lien ou sur le bouton "Visit site" pour accéder à votre projet déployé. /// Go to your repository on github. Go to tab ```Settings```, then in ```Pages``` in side menu. You will find an inset that indicates "Your site is live at {{link_of_site}}". Clic on link or on the button "Visit site" to access to your deployed project.
