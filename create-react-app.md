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

13. Öppna ```/src/app.js```
14. Notera

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

15. Besvara *I vilken datatyp är innehållet i ```return``` skrivet?*
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
4. 

# En första React Component

1. Installera extension ```Simple React Snippets``` ab Burke Holland
1. Skapa mappen ```/src/components```
2. Skapa filen ```counter.jsx``` där
3. I filen skriv ```imrc```
4. ```cc```
5. Använd multiradersfunktionen (markera + alt, esc avslutar) och ge klassen ett namn

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

6. Ersätt ```return``` med ```return JSX```
7. ```return <h1>Hello from component</h1>```

24. ```npm i bootstrap```
25. 
