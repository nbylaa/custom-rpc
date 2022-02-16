# ✨ ┊ Custom RPC

Do you want a custom discord rich presence like [this](https://raw.githubusercontent.com/nbylaa/custom-rpc/main/assets/Screenshot_2022_0213_064935.png?token=GHSAT0AAAAAABPVRM4XHAN2I4XARZCXMLR2YQIJQHA)?

I will give the tutorial (I suggest you use this code in [replit](https://replit.com/repls))

☁️ The language used in this code is [`NodeJS`](https://nodejs.org)

Steps to Make RPC:

#1 ┊ [Uploading assets](https://github.com/nbylaa/custom-rpc/blob/main/README.md#1--uploading-assets)

#2 ┊ [Setting up tokens](https://github.com/nbylaa/custom-rpc/blob/main/README.md#2--setting-up-tokens)

#3 ┊ [Installing the package](https://github.com/nbylaa/custom-rpc/blob/main/README.md#3--installing-the-package)

#4 ┊ [Start Making RPC](https://github.com/nbylaa/custom-rpc/blob/main/README.md#4--start-making-rpc)

#5 ┊ [Make it active 24/7](https://github.com/nbylaa/custom-rpc/blob/main/README.md#5--make-it-active-247)

## #1 ┊ Uploading assets
You have to upload an image to be your rpc asset, upload it on [Discord Dev Portal](https://discord.com/developers/applications)

📝 Assets cannot be edited, if you want to change the asset name, you must delete and re-upload the asset to your application

## #2 ┊ Setting up tokens
To use this code, you must have your discord account token, want to know how? Please watch this [video](https://youtu.be/IVZzyjYyUkc)

⚠️ Don't give your token to others, your account might be hacked, change your password to regenerate tokens

## #3 ┊ Installing the package
You only need 2 packages to make this rpc
```js
npm i discord.js-selfbot-v11
npm i discordrpcgenerator
```

## #4 ┊ Start Making RPC
```js
const discord = require ("discord.js-selfbot-v11");
const rpc = require ("discordrpcgenerator");
```
You have to enter your token, twitch link and app id into the environment
```js
const { token, app_id, twitch } = process.env;
```
```js
const client = new discord.Client();
client.login(token);

client.on("ready", () => {
ㅤrpc.getRpcImage(app_id, "your_asset_name").then(large => {
ㅤㅤsetInterval(() => {
ㅤㅤㅤclient.user.setPresence({
ㅤㅤㅤㅤgame: {
ㅤㅤㅤㅤㅤname: "activity_name",
ㅤㅤㅤㅤㅤtype: 1,//Choose the type of activity in the form of numbers (https://discord.com/developers/docs/game-sdk/activities#data-models-activitytype-enum)
ㅤㅤㅤㅤㅤurl: twitch, //Enter this if you want to set streaming status
ㅤㅤㅤㅤㅤapplication_id: app_id,
ㅤㅤㅤㅤㅤassets: { large_image: large.id },
ㅤㅤㅤㅤㅤdetails: "activity_details",
ㅤㅤㅤㅤㅤstate: "activity_state"
ㅤㅤㅤㅤ}
ㅤㅤㅤ}).then(activity => {
ㅤㅤㅤㅤconsole.log(`\n✨ ┊ Refresh\n{ timestamp: ${Date.now()} }`);
ㅤㅤㅤ}).catch(e => {
ㅤㅤㅤㅤconsole.log(`\n🚧 ┊ Disconnected\n { timestamp: ${Date.now()} }`);
     })
ㅤㅤ}, 16000)
ㅤ})
});
```
Wait 10-15 seconds until your rpc appears

## #5 ┊ Make it active 24/7
Do you want the rpc to always active?, enter this code

```js
require("http").createServer((_, res) => res.end("Uptime!")).listen(3000)
```
Put your website hosting on [Uptimerobot](https://uptimerobot.com)
