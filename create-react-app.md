

1. Skapa mapp och flytta dit | Från mapp skriv ```create react-app react-app```
2. I VS Code ```npx create-react-app .```
3. Notera...
4. ```npm start``` - startar utvecklingsmiljön
5. ```npm run build``` - skapar en deploymentmiljö
6. ```npm test``` - Startar testläge
7. Starta ```npm start```
8. Öppna ```/public/index.html```
9. Notera ```<div id="root"></div>```
6. Öppna ```/public/index.js```
1. Notera ```import App from './App';```
1. Notera...

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

15. Besvara *I vilken datatyp är innehållet skrivet?*

16. ```npm i bootstrap```
9. 
