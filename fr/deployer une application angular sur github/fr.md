# Déployer un projet angular sur github

### 1) Créez une branche ```gh-pages```

```
git checkout -b gh-pages
```

### 2) Ajoutez la branche au repository

```
git push origin gh-pages
```

### 3) Retournez sur la branche ```main```

```
git checkout main
```

### 4) Installez la dépendance angular

```
nd add angular-cli-ghpages
```

### 5) Créez le dossier ```dist``` qui contiendra le code de votre projet en production

```
ng build --configuration production --base-href=https://{{nom_de_domaine}}/{{nom_du_projet}}/
```
#### Note : n'oubliez pas le dernier ```/``` à la fin du lien

### 6) Faîtes un commit du dossier ```dist``` sur la branche gh-pages et lancez le déploiement

```
npx angular-cli-ghpages --dir=dist/{{nom_du_dossier}}
```
#### Note : Le chemin passé en argument de ```--dir``` soit contenir un fichier ```index.html```. Si l'étape 5 a créé un dossier ```browser``` qui contient ce fichier, ajoutez le au chemin.

### 7) Rendez-vous sur votre repository sur github. Allez dans l'onglet ```Settings```, puis dans ```Pages``` dans le menu latéral. Vous trouverez un encadré qui indique "Your site is live at {{lien_du_site}}". Cliquez sur le lien ou sur le bouton "Visit site" pour accéder à votre projet déployé.