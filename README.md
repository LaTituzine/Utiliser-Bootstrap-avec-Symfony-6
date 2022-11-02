
# Utiliser Bootstrap dans une application Symfony 6

Comment utiliser Bootstrap dans une application Symfony 6.


*Pré-requis* : 
- Avoir créé une application Symfony 6
- Avoir installé le bundle Webpack Encore

## Les différentes étapes 

1. **Modifier l'extension du fichier *app.css* en *app.scss***
Ce fichier se trouve dans *assets/styles*

2. **Modifier le fichier app.js**
Comme nous avons modifié l’extension du fichier *app.css* il faut la mettre à jour dans le fichier *app.js* qui se trouve dans le dossier *assets*
```javascript
import '.styles/app.scss'
```

3. **Activer Sass**
Dans le fichier *webpack.config.js*, activer la ligne *.enableSassLoader()*
```javascript
.enableSassLoader()
```

4. **Compiler les fichiers**
```
$ npm run watch
```
Cela va générer un message d'erreur dans le terminal demandant l'installation de sass-loader et sass. Suivre la procédure d'installation. Avec npm la commande est la suivante :
```
$ npm install sass-loader@^12.0.0 sass --save-dev
```
Puis recompiler les fichiers :
```
$ npm run watch
```

5. **Installer Bootstrap**
```
npm install bootstrap --save-dev
```

6. **Importer les styles Bootstrap dans le fichier *app.scss***
```scss
// le ~ permet de faire référence aux éléments dans node_modules
@import "~bootstrap/scss/bootstrap";
```

7. **Importer le JS**
Ajouter la ligne suivante dans app.js
```javascript
import "bootstrap";
```

8. **Utiliser les icones de Bootstrap**
- Installer bootstrap-icons
```
npm i bootstrap-icons
```
Cela crée un dossier *bootstrap-icons* dans */node_modules*
- Importer bootstrap-icons dans *app.scss*
```scss
@import "~bootstrap-icons/";
```

## Documentation Symfony

- <https://symfony.com/doc/current/frontend/encore/simple-example.html#using-sass-less-stylus>
- <https://symfony.com/doc/current/frontend/encore/css-preprocessors.html>
- <https://symfony.com/doc/current/frontend/encore/bootstrap.html>