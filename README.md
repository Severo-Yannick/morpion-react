# morpion-react

- 1  Assurez-vous de disposer d’une version installée de Node.js suffisamment récente.

- 2 Créer un nouveau projet 👉  `npx create-react-app my-app`
```bash
  Success! Created morpion at /Users/yannick/Documents/Racine/React/Pratique/morpion-react/morpion
Inside that directory, you can run several commands:

  npm start
    Starts the development server.

  npm run build
    Bundles the app into static files for production.

  npm test
    Starts the test runner.

  npm run eject
    Removes this tool and copies build dependencies, configuration files
    and scripts into the app directory. If you do this, you can’t go back!

We suggest that you begin by typing:

  cd morpion
  npm start

Happy hacking!
```

- 3 Supprimez tous les fichiers du dossier src/ présent dans le nouveau projet.
Ne supprimez pas le dossier src lui-même, juste les fichiers sources à l’intérieur.

```bash
yannick@MacBook-Pro morpion-react % cd morpion 
yannick@MacBook-Pro morpion % cd src 
yannick@MacBook-Pro src % touch index.css
yannick@MacBook-Pro src % 
```

- 4 Ajoutez un fichier nommé index.css dans le dossier src/ et mettez-y ce code CSS.
```css
body {
  font: 14px "Century Gothic", Futura, sans-serif;
  margin: 20px;
}

ol, ul {
  padding-left: 30px;
}

.board-row:after {
  clear: both;
  content: "";
  display: table;
}

.status {
  margin-bottom: 10px;
}

.square {
  background: #fff;
  border: 1px solid #999;
  float: left;
  font-size: 24px;
  font-weight: bold;
  line-height: 34px;
  height: 34px;
  margin-right: -1px;
  margin-top: -1px;
  padding: 0;
  text-align: center;
  width: 34px;
}

.square:focus {
  outline: none;
}

.kbd-navigation .square:focus {
  background: #ddd;
}

.game {
  display: flex;
  flex-direction: row;
}

.game-info {
  margin-left: 20px;
}

```

- 5 Ajoutez un fichier nommé index.js dans le dossier src/ et mettez-y ce code JS.
```bash
yannick@MacBook-Pro src % touch index.js
```
 ```js
 class Square extends React.Component {
  render() {
    return (
      <button className="square">
        {/* TODO */}
      </button>
    );
  }
}

class Board extends React.Component {
  renderSquare(i) {
    return <Square />;
  }

  render() {
    const status = 'Next player: X';

    return (
      <div>
        <div className="status">{status}</div>
        <div className="board-row">
          {this.renderSquare(0)}
          {this.renderSquare(1)}
          {this.renderSquare(2)}
        </div>
        <div className="board-row">
          {this.renderSquare(3)}
          {this.renderSquare(4)}
          {this.renderSquare(5)}
        </div>
        <div className="board-row">
          {this.renderSquare(6)}
          {this.renderSquare(7)}
          {this.renderSquare(8)}
        </div>
      </div>
    );
  }
}

class Game extends React.Component {
  render() {
    return (
      <div className="game">
        <div className="game-board">
          <Board />
        </div>
        <div className="game-info">
          <div>{/* status */}</div>
          <ol>{/* TODO */}</ol>
        </div>
      </div>
    );
  }
}

// ========================================

ReactDOM.render(
  <Game />,
  document.getElementById('root')
);
```

- 6 Ajoutez les trois lignes suivantes tout en haut du index.js dans le dossier src/ :
```js
import React from 'react';
import ReactDOM from 'react-dom';
import './index.css';
```
Vous pouvez maintenant exécuter npm start dans le dossier (morpion) du projet et ouvrir http://localhost:3000 dans votre navigateur, ce qui devrait vous afficher un plateau de morpion vide. 😎
```bash 
Compiled successfully!

You can now view morpion in the browser.

  Local:            http://localhost:3000
  On Your Network:  http://172.20.10.6:3000

Note that the development build is not optimized.
To create a production build, use npm run build.
```

### 1. Ouvrez src/index.js dans votre dossier morpion
Nous avons fourni la mise en forme CSS afin que vous puissiez vous concentrer sur l’apprentissage de React et la programmation du jeu de morpion.

En examinant le code, vous remarquerez que nous avons trois composants React :

- Square
- Board
- Game

Le composant Square affiche un unique `<button>` et le Board affiche 9 cases. Le composant Game affiche un plateau avec des valeurs temporaires que nous modifierons plus tard. À ce stade, aucun composant n’est interactif.

👋 suivre les commits...


