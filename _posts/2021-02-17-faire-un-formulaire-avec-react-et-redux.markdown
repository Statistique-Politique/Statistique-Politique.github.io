---
layout: post
title:  "Faire un formulaire avect react et redux"
date:   2021-02-17 14:30:53 +0100
categories: programation
---

En partenariat avec les jeunes socialistes j'ai créé un simulateur d'aides sociales.
Ce simulateur marche en deux phases, durant la première phase l'utilisateur répond à des questions.
Selon les questions précédentes seuls des questions pertinentes sont séléctionés. À la fin, seuls les aides pertinentes sont proposés. 


Dans ce tutoriel nous allons voir comment mettre en place le code pour réaliser ce projet. 


# Fabriquer l'interface avec React


Pour gérer l'interface nous allons utiliser react. Cette outil est idéal pour quand l'apparence doit évoluer en fonction des interactions de l'utilisateur. De plus nous allons programmer avec typescript, un langage qui permet d'éviter plusieurs faiblesses du javascript tout en réstant très similaire.

## Installation de react

Malheuresement le choix des outils nous oblige à avoir une étape de compilation avant d'utiliser l'app. Pas possible de modifier directement les fichiers comme on peut être habitué dans d'autres projets web. 


Il va falloir [installer node.js](https://nodejs.org/en/) sur votre machine. Puis sur un terminal de console, écrire :


{% highlight bash %}
npx create-react-app nom-app --template typescript
{% endhighlight %}


Ceci va créer un dossier `nom-app` qui contient le code et les outils nécessaires pour compiler et tester l'app. Pour plus d'informations sur l'outil `create-react-app` voir [ici](https://create-react-app.dev/). Rentrons dans ce dossier en tapant dans la ligne de commande,

{% highlight bash %}
cd nom-app
{% endhighlight %}


Il nous suffit de lancer l'application, 
{% highlight bash %}
yarn start
{% endhighlight %}

Normalement, une fenètre s'est ouverte dans le navigateur à l'adresse [localhost:3000/](http://localhost:3000/).


<figure>
   <img src="/assets/react-formulaire/exemple_app.png"
      alt="Image du site" />
   <figcaption>Voici à quoi ressemble l'application après les premières étapes.</figcaption>
</figure>


On remarque que le site nous propose d'éditer `src/app.tsx`, faisons cela !


## Les questions


Bien maintenant que nous avons préparé notre environement de dévelopement, on peut commencer à coder. Regardons ce que contient le fichier `src/app.tsx`


{% highlight typescript %}
import React from 'react';
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.tsx</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
{% endhighlight %}

On remarque que à l'intérieure du return on a quasiment tout l'html de la page. On va partir de zéro et construire à partir de la. Remplacer le code de `src/app.tsx` par 

{% highlight typescript %}
import React from 'react';

function App() {
  return (
    <div>Hello world !</div>
  );
}

export default App;
{% endhighlight %}

Vous pouvez aller voir l'app sur [localhost:3000/](http://localhost:3000/) normalement la page se met à jour en temps réel mais il vous faudra peut-être recharger la page. La page fait un petit peu vide, ajoutons des questions !


Un des interets du 






Un des intéret de react, celui de pouvoir mélanger du code typescript (ou javascript) et de l'HTML sans grande difficultés. Quand on veut exécuter du code typescript pour générer un élément on le met entre accolades comme pour `{logo}`.


