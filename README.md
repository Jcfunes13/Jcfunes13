config.json

{
"token":"5107398441:AAFoLM3DHZ8LLcpaheUOqq0AA21uGYblrnU",
"prefix":"."

}

instalar :
npm install discord.js --save
npm init -y

codigo de server.js:
//ESTE CODIGO NO AFECTARA SU BOT, SCRIPT DE ARRANQUE

const http = require('http');
const express = require('express');
const app = express();

//
app.use(express.static('public'));

app.get("/", function (request, response) {
response.sendFile(__dirname + '/views/index.html');
});

app.get("/", (request, response) => {
response.sendStatus(200);
});

app.listen(process.env.PORT);

setInterval(() => {
http.get(`http://${process.env.PROJECT_DOMAIN}.glitch.me/`);
}, 60000);

const Discord = require("discord.js");
const client = new Discord.Client();
const config = require("./config.json");

client.on("ready", () => {
console.log("El bot está ENCENDIDO y Funcionando!" );
  });

client.on("message", (message) => {
     if(message.content === "tu comando") {
    }
    });
Client.login(config.token);
codigo de whatch.json:

{
"install": {
  "include": [
    "^package\\.json$",
    "^\\.env$"
  ]
},

"restart": {
  "exclude": [
    "^public/",
    "^dist/"
  ],

  "include": [
    "\\.js$",
    "\\.json"
  ]
},
"throttle": 9
}
