## Organisation

[Ma carte](https://macarte.ign.fr/) est un ensemble d'applications web développées par l'[Institut National de l'Information Géographique et Forestière (IGN)](https://www.ign.fr/) pour la création et le publication de carte en ligne.

Il est constitué d'une partie serveur développée avec [Symfony](https://symfony.com/) qui [intègre une API](https://github.com/IGNF-Ma-carte/macarte-api) et d'applications web pour [l'affichage et l'édition de cartes](https://github.com/IGNF-Ma-carte#-alpha-test-instance-on-github). Ces dernières s'appuient sur une bibliothèque ([mcutils](https://github.com/IGNF-Ma-carte/mcutils)) commune.

<p align="center">
  <img src="https://raw.githubusercontent.com/IGNF-Ma-carte/.github/main/img/organisation.png" width=800 />
</p>

### Les web applications

L'outil de [visualisation](https://github.com/IGNF-Ma-carte/mcviewer) peut être déporté pour afficher les cartes via un système de fichier, en dehors de l'infrastructure Ma carte.

## Intégration des cartes

Les cartes produites sur Ma carte peuvent être intégrées dans une page web via une iframe.   

### iFrameAPI

L' **iFrameAPI Macarte permet** d'intégrer une carte sur votre site web sous forme de widget et de la contrôler en Javascript.

l'API Player iFrame publie les cartes sur votre page dans une balise `<iframe>`. 
Les fonctions de l'API JavaScript vous permettent d'ajouter de controler l'affichage des cartes (position, zoom, etc.) de leurs ajouter de nouveaux outils (outils d'édition) et de récupérer des informations sur celles-ci (objets sélectionnés).
Vous pouvez également ajouter des écouteurs d'événements qui s'exécutent en réponse à certains événements déclenchés sur la carte, tels que la modification les déplacements, la création ou la sélection d'un objet.

Pour plus d'informations, voir la [documentation en ligne](https://ignf-ma-carte.github.io/mcviewer/doc/)
