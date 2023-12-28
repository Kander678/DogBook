# Dogbook

Dogbook is Facebook like social media for dog owners

# Zarządzanie projektem:

# Inicjowanie projektu:

- zainicjowanie bierzącego folderu jako projektu (utworzenie package.json)
  ```
  npm init
  ```
  (w przypadku nie przechodzenia przez konfigurację trzeba `npm init -y`)
- utworzenie "index.js" zajmującego się rootowaniem poszczególnych tras do zasobów:

  ```
  const path = require("path");
  const express = require('express');
  const app = express();
  const PORT = 3000;
  const bodyParser = require('body-parser');//do obsługi pobierania wartości POST z ciała zapytania

  app.use(express.json());
  app.use(bodyParser.urlencoded({extended:true}));

  app.get("/home",(req,res)=>{
      res.send("Strona domowa!");
      //res.sendFile(path.join(__dirname,"home.html"))
  })

  app.listen(PORT, () => {
      console.log(`Serwer uruchomiony na porcie ${PORT}`);
  });
  ```

- dodanie zależności (pakietów):

  - express (niezbędne):
    ```
    npm install express --save
    ```
  - dodanie nodemon (do automatycznego przeładowywania):
    ```
    npm install nodemon --vade-dev
    ```
    trzeba też dodać wpis w scripts:
    ```
    "start": "nodemon index.js",
    "dev": "nodemon index.js",
    ```

- uruchomienie serwera node poleceniem:
  ```
  npm start
  ```
  (można też "node index.js" ale to unika użycia skryptów uruchomieniowych, które mają nodemona do auto reload)
  #Autoryzacja dla przykładowego użytkownika:
  Email: pomelo@mail.com
  Hasło: pomelo
