## Organisation

[Ma carte](https://macarte.ign.fr/) est un ensemble d'applications web développées par l'[Institut National de l'Information Géographique et Forestière (IGN)](https://www.ign.fr/) pour la création et le publication de carte en ligne.

Il est constitué d'une partie serveur développée avec Symfony qui [intègre une API](https://github.com/IGNF-Ma-carte/macarte-api) et d'applications web pour [l'affichage et l'édition de cartes](https://github.com/IGNF-Ma-carte#-alpha-test-instance-on-github). Ces dernières s'appuient sur une bibliothèque ([mcutils](https://github.com/IGNF-Ma-carte/mcutils)) commune.

<p align="center">
  <img src="https://raw.githubusercontent.com/IGNF-Ma-carte/.github/main/img/organisation.png" width=800 />
</p>

Les cartes produites sur Ma carte peuvent être intégrée dans une page web via une iframe.   
Une [IFrameAPI](https://ignf-ma-carte.github.io/mcviewer/doc/) qui permet de piloter la carte en Javascript.

L'outil de [visualisation](https://github.com/IGNF-Ma-carte/mcviewer) peut être déporté pour afficher les cartes via un système de fichier.
