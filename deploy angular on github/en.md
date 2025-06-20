# Deploy angular projet on github

### 1) Create a ```gh-pages``` branch

```
git checkout -b gh-pages
```

### 2) Add the branch to repository

```
git push origin gh-pages
```

### 3) Return on ```main``` branch

```
git checkout main
```

### 4) Install angular dependency 

```
nd add angular-cli-ghpages
```

### 5) Create the folder ```dist``` which will contain the code of your project in production 

```
ng build --configuration production --base-href=https://{{nom_de_domaine}}/{{nom_du_projet}}/
```
#### Note : Don't forget the last ```/``` at the end of link

### 6) Commit the folder ```dist``` on the branch ```gh-pages``` and launch deployment

```
npx angular-cli-ghpages --dir=dist/{{nom_du_dossier}}
```
#### Note : The folder passed in argument of ```--dir``` must contain a file ```index.html```. If step 5 created a folder ```browser``` which contains the file, add it to path.

### 7) Go to your repository on github. Go to tab ```Settings```, then in ```Pages``` in side menu. You will find an inset that indicates "Your site is live at {{link_of_site}}". Clic on link or on the button "Visit site" to access to your deployed project.