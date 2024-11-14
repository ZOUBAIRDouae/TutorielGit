<!-- 
GitHub Pages est un service proposé par GitHub pour héberger des sites web directement à partir d'un dépôt GitHub. Il est particulièrement utilisé pour héberger des sites statiques, souvent créés avec du HTML, CSS et JavaScript, mais il peut également fonctionner avec des générateurs de sites statiques comme Jekyll, qui facilite la gestion des layouts.

Fonctionnement de GitHub Pages avec un Layout
Création du dépôt : Pour commencer, vous créez un dépôt sur GitHub qui contiendra le code source de votre site. Ce dépôt peut être public ou privé, mais seul un dépôt public sera accessible directement en ligne avec GitHub Pages.

Activation de GitHub Pages :

Dans les paramètres de votre dépôt, sous l’onglet "Pages", vous pouvez sélectionner la branche et, éventuellement, le dossier (par exemple, /docs) où se trouve le code source de votre site.
GitHub Pages va ensuite automatiquement détecter le code et générer une URL pour votre site, généralement sous la forme https://votre-nom-utilisateur.github.io/nom-du-depot/.
Utilisation de Jekyll pour le Layout :

GitHub Pages est compatible avec Jekyll, un générateur de site statique. Jekyll permet d’utiliser des layouts pour structurer votre site de manière modulaire.
Les layouts se trouvent dans le dossier _layouts. Vous pouvez y créer des fichiers comme default.html, qui serviront de structure de base pour vos pages.
Chaque page utilise un layout défini dans l'en-tête YAML (la section en haut du fichier, entre ---) comme suit :
yaml
Copier le code
---
layout: default
title: "Titre de la page"
---
Le layout va contenir des balises Jekyll, par exemple {{ content }}, pour indiquer où le contenu de chaque page spécifique sera inséré dans la structure globale du site.
Configuration du fichier _config.yml :

Dans ce fichier, vous pouvez définir des variables globales (comme le nom de votre site ou des liens de navigation) et configurer d’autres aspects de votre site. Cela facilite la personnalisation et la gestion de votre site sans modifier chaque page individuellement.
Personnalisation et thème :

GitHub Pages propose des thèmes Jekyll intégrés que vous pouvez activer via _config.yml, ou bien vous pouvez créer vos propres fichiers de style (CSS, JavaScript) pour personnaliser votre layout.
Publication automatique :

À chaque fois que vous poussez une mise à jour dans la branche choisie, GitHub Pages reconstruit automatiquement le site. Cela permet de mettre à jour le site simplement en travaillant sur les fichiers dans votre dépôt.
En résumé, GitHub Pages est un moyen pratique d’héberger des sites statiques et d'utiliser des layouts pour uniformiser le design, surtout avec Jekyll, qui permet de structurer et de gérer les pages du site de manière cohérente et modulaire.






Vous avez dit :
donnez-moi un example pratique comme un tutoriel pour presenter  dans la class a mon prof
ChatGPT a dit :
ChatGPT
Pour présenter un tutoriel pratique sur GitHub Pages avec un layout à votre professeur, voici un plan détaillé avec des étapes claires et du code. Ce tutoriel guide la création d’un mini-site en utilisant GitHub Pages et Jekyll pour appliquer un layout basique.

Tutoriel : Créer un mini-site avec GitHub Pages et un Layout
Objectif
Créer un site statique simple hébergé sur GitHub Pages en utilisant un layout avec Jekyll pour structurer le contenu.

Pré-requis
Un compte GitHub.
Connaissance de base de GitHub (créer un dépôt, pousser des commits).
Étapes
Étape 1 : Créer un dépôt GitHub pour le site
Connectez-vous à votre compte GitHub.
Créez un nouveau dépôt et nommez-le votre-nom-utilisateur.github.io (en remplaçant votre-nom-utilisateur par votre nom d’utilisateur GitHub).
Cochez l'option "Initialize this repository with a README" pour ajouter un fichier README.md.
Cliquez sur Create repository.
Étape 2 : Activer GitHub Pages
Allez dans les Settings du dépôt.
Dans la section Pages, sélectionnez la branche main (ou master, selon votre configuration).
Choisissez la source /(root) pour dire à GitHub Pages de prendre les fichiers depuis la racine du dépôt.
Cliquez sur Save. GitHub Pages va générer un lien pour votre site, généralement sous la forme https://votre-nom-utilisateur.github.io.
Étape 3 : Configurer Jekyll pour le Layout
Dans votre dépôt, créez un dossier nommé _layouts.

Dans _layouts, ajoutez un fichier default.html. Ce fichier sera le layout principal que Jekyll utilisera pour structurer chaque page.

Ajoutez le code suivant dans default.html :

html
Copier le code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{{ page.title }}</title>
    <link rel="stylesheet" href="/style.css">
</head>
<body>
    <header>
        <h1>Mon Site avec GitHub Pages</h1>
        <nav>
            <a href="/">Accueil</a>
            <a href="/about.html">À propos</a>
        </nav>
    </header>
    <main>
        {{ content }}
    </main>
    <footer>
        <p>&copy; 2024 - Créé avec GitHub Pages et Jekyll</p>
    </footer>
</body>
</html>
Ici, {{ page.title }} affiche le titre de chaque page, et {{ content }} insère le contenu spécifique de chaque page.
Étape 4 : Créer des Pages avec le Layout
Créez un fichier nommé index.md dans la racine du dépôt. Ce fichier représente la page d’accueil.

Ajoutez le code suivant dans index.md :

yaml
Copier le code
---
layout: default
title: "Accueil"
---
# Bienvenue sur mon site !
Ceci est la page d'accueil de mon site hébergé sur GitHub Pages avec Jekyll.
Créez une autre page en ajoutant un fichier about.md dans la racine du dépôt. Ce fichier représentera une page "À propos".

Ajoutez le code suivant dans about.md :

yaml
Copier le code
---
layout: default
title: "À propos"
---
# À propos de moi
Voici une page pour parler de moi ou de mon projet.
Étape 5 : Ajouter un fichier CSS pour la personnalisation
Créez un fichier nommé style.css à la racine du dépôt.

Ajoutez-y des styles de base, par exemple :

css
Copier le code
body {
    font-family: Arial, sans-serif;
    max-width: 800px;
    margin: auto;
    padding: 10px;
}
header {
    text-align: center;
    margin-bottom: 20px;
}
nav a {
    margin: 0 10px;
    text-decoration: none;
    color: #333;
}
footer {
    text-align: center;
    margin-top: 20px;
    font-size: 0.8em;
}
Étape 6 : Pousser les changements et vérifier le site
Si vous avez travaillé localement, poussez les fichiers dans votre dépôt GitHub.
Allez sur l'URL fournie par GitHub Pages (https://votre-nom-utilisateur.github.io) pour voir votre site.
Résultat
Vous avez maintenant un mini-site fonctionnel, avec une page d’accueil et une page "À propos", toutes deux utilisant le même layout default.html pour garantir une structure cohérente.

Présentation de votre travail
Expliquez chaque étape : Lors de votre présentation, suivez les étapes ci-dessus et montrez chaque fichier et son contenu.
Montrez le résultat : Ouvrez l’URL du site pour montrer à votre professeur comment le site s'affiche.
Parlez de l’organisation : Expliquez comment le layout (_layouts/default.html) structure chaque page en utilisant {{ content }} pour insérer le contenu dynamique. -->
