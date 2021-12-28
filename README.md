# react-tutor
En första studie av React

## Systemet

* React kommer från Facebook (2013)
* React mest populär. Angular och Vue är andra
* React är ett library, Angular är ett framework
* Components - isolerade delar av UI
* Root Component är oftast App
* App innehåller andra Components i ett träd av Components
* En Component skrivs som en Class och innehåller state = {}; och render() {...}

```class Like {
  state = {};
  render() {  --> React Element
  }
}
```

* React Element är en virtuell version av DOM som finns i minnet
* React reagerar på state förändringar och uppdaterar DOM
* React view ska vara uppdaterat enligt dess state



## Installera

* Uppdatera ```node```
* ```npx create-react-app .``` eller ```create-react-app react-app```


* ```npm start``` för att starta
* ```npm run build``` skapar production
* developer - production state

VS Code extensions
* Simple React Snippets
* Prettier - Code formatter

