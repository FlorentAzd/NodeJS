# NodeJS

`NodeJS` est un FrameWork Javascript coté serveur, il est utilisé dans la création de serveur WEB ainsi que d'API.

## Dépendances à installer (Linux)

### Nodejs

```bash
sudo apt-get install nodejs
```

### npm
```bash
sudo apt-get install npm
```

## Mise en place de l'environnement

### Initialisation du répertoire de travail.

Avant de pouvoir creer notre première application nodejs, il est nécéssaire de creer nun réperoire de travail dans lequel seront conserver les paquets à installer.

Pour cela
```bash
mkdir my-node-app && cd my-node-app && npm init -y
```

### Code du serveur
Creer ensuite un fichier `index.js` et y ajouter les lignes suivantes :
```Javascript
// On ajoute le module http nécesaire à la creation du serveur
var http = require("http")

// On cree ensuite notre serveur grace à la méthode `createServer()`
// Cette ligne est appelé à chaque nouvelle connexion au serveur
var server = http.createServer(function(req, res){
  // On précise les entetes
  // 200 : valeur de retour OK
  // Content-Type : Le type de fichier envoyer à l'utilisateur
  // charset : l'encodage du fichier
  res.writeHead(200, {"Content-Type": "text/html; charset=utf-8"})
  // res.writeHead est une methode optionnelle

  res.end("<h1>Hello world<h1>")
  // On envoie ensuite Hello world à l'utilisateur
});

// Pour qu'on puisse faire tourner notre server on utilise la méthode `liste` et on précise le port d'écoute, ici : 8080
server.listen(8080, function(){
  console.log("Le serveur tourne...")
})
```
## Demarrage du serveur
Pour finir on lance notre serveur
```bash
node index.js
```
