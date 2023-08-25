# Installation & développement

Sauf indication contraire les web applications sont développées de la même manière.

## Installation

Ils utilisent npm pour la gestion des dépendance.   
Lors de la première installation, configurer la sauvegarde des mots de passe dans le système.
```
npm git config --global credential.helper store
```
Puis lancez l'installation des dépendance (à la première installation le login mot de passe du gitlab vous sera demandé)
```
npm install
```

### Developper derrière un proxy

💡 En cas de problème, ne pas oublier de configurer le proxy. En variable d'environnement sous Windows:
```
set HTTP_PROXY=http://username:password@proxy.example.com:1234
set HTTPS_PROXY=http://username:password@proxy.example.com:1234
```
Ou bien dans Node:
```
npm config set http-proxy "http://username:password@proxy.example.com:1234/"
npm config set https-proxy "http://username:password@proxy.example.com:1234/"
```

### Mise à jour de mcutils

Les web applications utilisent la bibliothèque [mcutils](https://github.com/IGNF-Ma-carte/mcutils).   
Lorsque celle-ci a été modifiée il peut être nécessaire de la mettre à jour.  
Idem pour mettre à jour les icones (font-ign) lorsque de nouvelles icones ont étés ajoutées.

```
npm update mcutils
npm update font-ign
```

La documentation de mcutils est disponible sur le [serveur de test](https://ignf-ma-carte.github.io/mcutils/doc/).

## Développement

### Outils et dépendances

Les projets sont développés en JS/ES6 et utilisent le bundler [ParcelJS](https://parceljs.org/) pour le transpilage et la compilation.

Les applications utilisent diverses technologies et bibliothèques JS.

* [OpenLayers](https://npmjs.com/package/ol) : pour l'affichage des cartes en JS
* [ol-ext](https://npmjs.com/package/ol-ext) : une extension pour Openlayers qui offre des outils 
* [PapaParse](https://npmjs.com/package/papaparse) : un parseur de fichier CSV dans le navigateur
* [SheetJS](https://www.npmjs.com/package/xlsx) : pour la lecture et l'export des fichiers Excel en JavaScript
* [Chart.js](https://npmjs.com/package/chart.js) : pour la création de diagrammes en ligne
* [Chroma-js](https://npmjs.com/package/chroma-js) : pour la gestion des couleurs (cartes statistiques)
* [highlight.js](https://npmjs.com/package/highlight.js) : une biblioithèque de coloration syntaxique
* [jsPDF](https://www.npmjs.com/package/jspdf) : pour l'écriture de fichiers PDF
* [docx](https://npmjs.com/package/docx) : pour l'enregistrement de documents world


### Lancement des tests

```
npm start
```
Les tests sont disponibles à l'adresse http://localhost:1234/

Les modules se mettent à jour automatiquement lors de chaque modification du code javascript ou du CSS et la page va se recharger.

### Fichiers de config

Le fichier de configuration à la racine du projet est automatiquement chargé par mcutils.   
Ce fichier est situé dans le répertoire assets/config.json.   
Vous pouvez modifier ce fichier pour vous connecter à un serveur spécifique si besoins (qualif ou prod)

> ⚠️ Assurez-vous que le serveur spécifié est bien celui de qualif avant de commiter le fichier pour éviter tout risque.

> 💡 En production (et qualif) un fichier de config spécifique vient automtiquement surcharger le fichier du projet.


### Analyse statique du code

Lors des développements lancez régulièrement l'analyse de code statique (lint) et corrigez les erreurs remontées.
```
npm run lint
```

## Création de l'application pour déploiement

Supprimer le répertoire `./docs` du projet et lancer :
```
npm run build
```
Le répertoire `./docs` contient le projet prèt à être déployé.
