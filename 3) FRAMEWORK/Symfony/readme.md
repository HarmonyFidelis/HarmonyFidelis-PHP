# Symfony

---

## Configuration

---

- PHP
- Composer
- Visual Studio Code
- Symfony CLI

---

## Installation

---

```text
symfony new my-project_name --full
```

## Architecture de Symfony5

- template: contiendrat nos vues (fichier.html)
- src :
  - Controller : Reçois requête traité par une route et renvois réponse appropriées
  - Entity : Class qui représente structure de nos tables dont les attributs représente les champs de notre table
  - Repository : Centralise la récupération de vos entity (tables)

```text
    |-- bin
    |-- config
    |-- migrations
    |-- public
    |-- src
        |-- Controller
        |-- Entity
        |-- Repository
    |-- templates
        |-- base.html.twig
    |-- tests
    |-- translations
    |-- var
    |-- vendor
    |-- .env
    |-- .env.test
    |-- .gitignore
    |-- composer.json
    |-- composer.lock
    |-- docker-compose.override.yaml
    |-- docker-compose.yaml
    |-- phpunit.xml.dist
    |-- symfony.lock
```

## Lancer votre serveur local

Dans le terminal

```text
symfony serve
```

---

## Création d'un page

---

Servez-vous pour cela de symfony console dans le terminal. Il vous permettra de créer rapidement du code a partir de ligne de commande.

```texte
symfony console
```

### Créer un controller

Dans le terminal

```texte
symfony console make:controller
```

- Nommé votre controller "NameController"

Le controller va créer la route avec le nom qu'on a donner à notre fichier et il va créer égalment notre vue dans templates

### Twig afficher nos vues aux utilisateurs

Le principe des twigs c'est d'édité un fichier base.html.twig un fichier contenant l'architecture html de toutes les pages.

```code
base.html.twig

{# Creation d'un fichier HTML de base #}

<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>{% block title %}{% endblock %}</title>
    </head>
    <body>
        <div class="content">
        {# Permet de créer une Architecteure de page qui sera appelez ou non sur un page #}
        {% block content %}
        {% endblock %}
        </div>
    </body>
</html>
```

Une fois cela fait il faurat importé notre base.html.twig dans nos fichier html contenant nos pages.

```code
index.html.twig

{# Permet d'importé le fichier base.html.twig dans index.html #}
{% extends "base.html.twig" %}

{# contenue visible dans index.html à l'emplacement archtectural de base.html.twig#}
{% block title %}Title de la page index{% endblock %}
{% block content %}
Ceci cera le contenu de ma page index
{% endblock %}
```

### Ajouter une variable à nos twig

Dite ou votre variable sera utilisé

```code
{# Permet d'importé le fichier base.html.twig dans index.html #}

{% extends "base.html.twig" %}

{% block content %}
    <h1>Bonjour {{ first_name }}</h1>
{% endblock %}

```

```code
<?php

namespace App\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\Routing\Annotation\Route;

class NameController extends AbstractController
{
    /**
     * @Route("/name", name="name")
     */
    public function index(): Response
    {
        // Ajouter un variable qui sera utilisé dans
        $firstname = "Jérémy";

        // Transfere votre variable à index.html.twig
        return $this->render('name/index.html.twig', [
            'firstname' => $firstname
        ]);
    }
}
```
