# Create-React-App

1. Skapa mapp och flytta dit | Från mapp skriv ```create react-app react-app```
2. I VS Code ```npx create-react-app .```
3. Notera...
4. ```npm start``` - startar utvecklingsmiljön
5. ```npm run build``` - skapar en deploymentmiljö
6. ```npm test``` - Startar testläge
7. ```npm eject``` - tar fram modules som är dolda. En en-vägs-operation. Går ej att ångra
8. Starta ```npm start```
9. Öppna ```/public/index.html```
10. Notera ```<div id="root"></div>```
11. Öppna ```/public/index.js``` entry point 
12. Notera ```import App from './App';```
13. Notera...

```
ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById('root')
);
```

14. Öppna ```/src/app.js```
15. Notera

```
function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
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
```

16. Besvara *I vilken datatyp är innehållet i ```return``` skrivet?*
17. Svar: JSX (JavaScript Syntax Extension) som möjliggör samma syntax som HTML
18. JSX är ett XML-tillägg som tillåter att skriva HTML liknande kod
19. JSX behöver kompileras (Babel) i en *transpiler* (kod till kod)
20. Testa att kompilera JSX i ```babeljs.io```
21. Notera ```React.createElement(...);``` som skapar element i React
22. ```/src/app.js``` är en component som skapar ett GUI

# Hello World

1. Radera alla filer i ```/src```
2. Skapa en ny fil ```/src/index.js```

```
import React from 'react';  //används för React.createElement
import ReactDOM from 'react-dom';

const element = <h1>Hello World</h1>; //JSX
console.log(element);
```

3. Öppna console och inspektera element. 
4. Detta skapade ```react.element``` som är en del av virtuella DOM i minnet
5. När react.element förändras, jämförs skillnaden med browser DOM och uppdaterar därefter
6. Ersätt console.log... med ```ReactDOM.render(element, document.getElementById('root'));```

# Installera Bootstrap

1. ```https://getbootstrap.com/docs/versions``` Flera versioner
2. Alternativ: ```npm install bootstrap@4.5```
3. I consolen ```npm install bootstrap``` för senaste

# En första React Component

1. Installera extension ```Simple React Snippets``` av Burke Holland
2. Skapa mappen ```/src/components```
3. Skapa filen ```counter.jsx``` där
4. I filen skriv ```imrc```
5. ```cc```
6. Använd multiradersfunktionen (markera + alt, esc avslutar) och ge klassen ett namn

```
import React, { Component } from 'react'

class Counter extends Component {   // Counter utökar Component som importeras från react
  state = {  } 
  render() { 
    return ();
  }
}
 
export default Counter;
```

7. Ersätt ```return``` med ```return JSX```
8. ```return <h1>Hello from component</h1>```
9. I ```src/index.js``` 
10. JavaScript lägger till ett osynligt ```return ;``` (semikolon) om inget finns efter return
11. Bädda in JSX inom ```(...)``` så fungerar det


```
import React from 'react';
import ReactDOM from 'react-dom';
import 'bootstrap/dist/css/bootstrap.css';
import  Counter from './components/counter';

//const element = <h1>Hello World 2</h1>; //JSX
ReactDOM.render(<Counter />, document.getElementById('root'));
```

# Inbäddade uttryck (Embedded expressions)

1. Prova att lägga till ytterligare HTML-liknande element i JSX i filen ```/src/component/counter.jsx```
2. Genererar felmmeddelande: JSX uttryck måste ha ett överliggande uttryck
3. Påminnelse om att React skapar ```React.createElement('h1')```
4. Testa uttrycken https://babeljs.io/repl med <div> omkring
5. Inspektera HTML-koden i webbläsaren, nu har vi två DIV's
6. Om detta är oönskat går det att ersätta DIV i JSX mot ```React.Fragment```
7. Inspektera
  
### Dynamiskt innehåll i JSX
  
1. Inom Component-filen lätt till ```count: 0``` inom State-objektet
2. Lägg till ```<span>{this.state.count}</span>``` inom return-argumentet
3. Inom ```{...}``` kan vilken valid JS skrivas som helst. T.ex. funktioner
4. Skapa funktionen
  
```
formatCount() {
  return this.state.count === 0 ? 'Zero' : this.state.count;
}
```

5. https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator
6. Ändra ```<span>{this.state.count}</span>``` till ```<span>{this.formatCount()}</span>```
  
### Attribut i JSX
  
7. Attribut kan vara dynamiska enligt principen ```<img src={this.state.imageUrl} alt="" />
8. CSS-klasser måste heta ```classname```
9. Definiera egna stilar genom...
  
```
styles = {
  fontSize: 10,
  fontWeight: bold
};
```
  
10. Alla CSS-stilar skrivs i camel-case
11. ```<span style={this.styles} ... </span>```
12. Eller ```<span style={{ fontSize: 20 }} ```
                   
### Dynamiska CSS-klasser
                   
```
let classes = "badge m-2 ";
classes += (this.state.count === 0) ? "bg-warning text-dark" : "bg-secondary";
```
                   
13. Markera raderna och Refactor till class Counter, döp till ```getBadgeClass```
14. Anropa ```<span className={this.getBadgeClasses()}>...</span>```
15. Radera ```let classes = this.getBadgeClasses();```

## Rendera dynamiska listor

1. Inom `render() { return })` ange 

```
<ul>
  { this.state.tags.map(tag => <li></li>)}
</ul>
```

2. Ovanstående genererar ett ´unique "key" error`
3. `<l1>` behöver ett ´key id´

```
{ this.state.tags.map(tag => <li key={tag}>{ tag }</li>)}
```

## Villkorlig rendering

1. Med en helperMethod kan JavaScript if testa villkor

```
renderTags() {
  if (this..state.tgs.length === 0) return <p>tomt</p>;  // eller ... return null
}

...

{ this.renderTags() }
```
Ett alternativ till...

```
{ this.state.tags.lenght === 0 && "tomt" }  // första delen blir ´true´ + boolesk AND 
```

## Hantera events

1. Använd JavaScript events i camelcase-format. `onclick` fungerar alltså inte.
2. Också, eventHandlers har inte tillgång till `this`
3. `this` följer inte med function() men följer obj.method().
4. Det är då Bind kommer in

## Bind Event handlers

```
constructor() {
  super();
  this.handleIncrement = this.handleIncrement.bind(this);
}
```

eller med arrow functions (som hanterar ´this´ annurlunda).


```
handleIncrement = () => {
  console.log('+ clicked', this);
}
```

* En normal funktion's ´this´ ärver från sitt förälder objekt (inom sitt scope)
* En arrow function ärver ´this´ från parent scope (ovanför sitt scope)

## Uppdatera state

```
handleIncrement = () => {
  this.setState({ count: this.state.count +1 })
}
```

* Ovan är `setState` av betydelse.

## Vad händer när State förändras?

1. Klick eventet anropar en arrow funktion som gör ´setState´
2. React schemalägger då ett asynkront anrop till `render() {}`
3. `render()` returnerar JSX i ett uppdaterat virtuellt DOM
4. React beräknar skillnaderna mellan Virtuell DOM och Browser DOM
5. Bara en skillnad finns i JSX-span i Virtuella DOM nämligen `{this.formatCount()}`
6. Att endast `span elementet` uppdateras går att se genom att inspektera HTML-koden


//Passing Event Arguments - 1:12:58 kommer upp

24. ```npm i bootstrap```
25. 
