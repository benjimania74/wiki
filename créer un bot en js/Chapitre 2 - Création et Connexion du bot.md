## Chapitre 2 - Création et Connexion

Bonjour à toi!
Dans ce chapitre tu vas apprendre à créer l'"utilisateur" de ton bot et a le lancer.
La plupart de ce chapitre ne concernera pas le code mais le code qui sera donné dans ce chapitre sera très important si tu veux, plus tard, créer un autre bot.
Aller! C'est parti!


# I) Création de l'utilisateur bot

Créer l'utilisateur bot est la chose la plus simple dans la création d'un bot Discord.
Pour ce faire:

- Aller sur le Portail Développeur de Discord (https://discord.com/developers/)
- Cliquer sur "New Application" en haut à droite de la page

![screenshot](https://cdn.discordapp.com/attachments/657979900560539658/823198014599462962/unknown.png)
- Donner un nom a l'application et la créer
- Aller dans l'onglet "Bot"

![screenshot](https://cdn.discordapp.com/attachments/657979900560539658/823198496295092224/unknown.png)
- Cliquer sur "Add Bot" puis sur "Yes, do It!"
- Changer l'image de profil si souhaité

La création de l'utilisateur bot est maintenant terminé

# II) Ajout du bot sur son Serveur

Pour ajouter le bot sur ton serveur il faut!

- Aller dans l'onglet "OAuth2" de ton Application (Developper Portal)

![screenshot](https://cdn.discordapp.com/attachments/657979900560539658/823199542915629096/unknown.png)
- Selectionner dans les "Scopes" (les cases a cocher) "bot"
- Décendre vers les nouvelles cases à cocher et cliquer sur "Administrator"
- Copier le lien donné et y acceder
- Ajouter le bot sur le serveur voulu

Maintenant il ne reste plus qu'a vérifier que votre bot soit bien sur le serveur

![screenshot](https://cdn.discordapp.com/attachments/657979900560539658/823202975953453106/unknown.png)

# III) Connexion

Maintenant et pour finir, tu vas apprendre a lancer ce petit bot!

- Pour commencer, lance ton éditeur de code. Si tu as la possibilité de choisir un dossier de travail, prends celui ou Discord.JS a été installé.
- Ensuite, créer un fichier avec comme extension "js" qui sera le fichier principal du bot. Il est conceillé de l'appeller "index", ce qui donnera le fichier "index.js".
- Ouvres ce fichier

Maintenant, c'est la partie code du bot!

En premier temps, il faut importer Discord.JS. Pour ce faire, il faut aller en haut du fichier et écrire:

```js
const Discord = require('discord.js');
```
Ce code nous permet d'avoir accès à la librairie dans le "index.js".
Avec seulement cette importation, tu vas pas pouvoir lancer ton bot. Elle permet de le lancer mais pas avec une ligne seulement.

Il faut donc créer une instance client. Pour ce faire, il faut ajouter sous l'importation de la librairie:
```js
const client = new Discord.Client();
```


Pour le moment le contenue du index.js est:

```js
const Discord = require('discord.js');
const client = new Discord.Client();
```


Maintenant, il faut permettre au bot de se connecter sur l'utilisateur créé précedement.
Pour ce faire, il faut:
- Aller sur notre Application dans le Developper Portal
- Aller dans l'onglet "Bot"
- Cliquer sur "Copy" sous "Click to Reveal Token"

![sceenshot](https://cdn.discordapp.com/attachments/657979900560539658/823219457991114792/unknown.png)

⚠ Le Token de votre bot ne doit pas être révellé! S'il venait à être révellé, changé le en appuyant sur le bouton "Regenerate"!


Dans le index.js, tout en bas de préférence pour que ça dérange moins (mais c'est pas obligé), ajoutes la ligne:

```js
client.login("TOKEN");
```
Remplaces TOKEN pas le token de ton bot.

Ce code permet simplment au bot de connaitre l'utilisateur ou se connecter.


Mais ce n'est pas tout. Si tu essaies de lancer le bot avec ce code, le bot ne se lancera pas...

Voyons maintenant la dernière ligne droite pour lancer le bot.

Avec Discord.JS, il y a plusieurs evenement. ready, guildMemberAdd, guildMemberRemove, message....

Pour lancer le bot c'est l'evenement "ready". Voici comment l'utiliser:

```js
client.on('ready', function() {
});
```

Maintenant le bot se lancera! Mais il vaut mieux recevoir un message pour être sur que le bot soit en ligne. 

On va transformer ce code en:

```js
client.on('ready', function() {
    console.log("Je suis en ligne");
});
```

Maintenant quand le bot s'allumera il le dira par un petit message!

Voici le code complet:

```js
const Discord = require('discord.js');
const client = new Discord.Client();

client.on('ready', function() {
    console.log("Je suis en ligne");
});

client.login("TOKEN");
```

# Lancement du bot

C'est bien beau d'avoir un code mais il faut l'executer quand même non?
Pour ce faire c'est très simple!

- Lancer l'invite de commande ou Termux si tu es sur téléphone
- Aller dans le répertoire où est mis le bot (```CD CHEMIN```)
- Executer la commande ```node .``` ou ```node index.js```
- Admirer le bot se lancer

![screenshot](https://cdn.discordapp.com/attachments/657979900560539658/823229406272552980/unknown.png)

![screenshot](https://cdn.discordapp.com/attachments/657979900560539658/823229810628886558/unknown.png)


# Bonus - Statue Personnalisé

Pour ce tuto, il y a un petit bonus. Il n'y sera surement pas à chaque fois. Ce bonus est là pour t'apprendre à mettre un statue personnalisé a ton bot!

Tout ce passe dans l'évenement "ready" (qui permet de lancer le bot). Le code est très simple

```js
client.user.setActivity('Activité', { type: 'PLAYING' });
```

PLAYING n'est pas le seul statue possible.

Voici la liste des statues marquable dans le "type":
- PLAYING
- LISTENING
- COMPETING
- STREAMING

#

C'est tout pour aujourd'hui! A la prochaine!

Par benjimania74
