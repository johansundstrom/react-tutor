# react-tutor
En första studie av React

## Systemet

* React kommer från Facebook (~2012)
* React mycket populär. Angular och Vue är andra
* React är ett library, Angular är ett framework
---
### Components

* Components - isolerade delar av UI
* Root Component är oftast ```App```
* ```App``` innehåller andra Components i ett *träd av Components*
* Components är återanvändningsbara
* En Component skrivs som en Class och innehåller state = {}; och render() {...} 

```class Like {
  state = {};
  render() {  --> React Element
  }
}
```

* state innehåller data som ska renderas
* render beskriver Components utseende

* React Element är en virtuell version av DOM som finns i minnet - Virtual DOM
* React reagerar på state förändringar och uppdaterar Browser DOM
  * State change in Virtual DOM --> compute diff to browser DOM --> Re-render Browser DOM 
* React view ska vara uppdaterat enligt dess state



## Installera

* Uppdatera ```node```
* ```npx create-react-app .``` eller ```create-react-app react-app``` eller ```npm i -g create-react-app```
* Installerar
  * Utvecklingsserver
  * Webpack
  * Babel


* ```npm start``` för att starta
* ```npm run build``` skapar production
* developer - production state

VS Code extensions
* Simple React Snippets - Burke Holland
* Prettier Code formatter - Esben Petersen

Installera Bootstrap
* ```npm install bootstrap```

## Components

* Alla delar i ett UI utgörs av React Components
* Composing components
  * Skapa ett träd av komponenter
  * Skapa en Component som importerar andra Components
  * Filnamn kan gärna döpas till plural
* En Component inleds med en import (snippet: IMRC)
* Därefter en class (snippet: CC)
* 

### Skicka data till Component

* 

## Skapa en React App

* ```create-react-app 
