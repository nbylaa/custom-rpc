# ✨ ┊ Custom RPC

Do you want a custom discord rich presence like [this](https://raw.githubusercontent.com/nbylaa/custom-rpc/main/assets/Screenshot_2022_0213_064935.png?token=GHSAT0AAAAAABPVRM4XHAN2I4XARZCXMLR2YQIJQHA)?

I will give the tutorial (I suggest you use this code in [replit](https://replit.com/repls)

## #1 ┊ Uploading assets
You have to upload an image to be your rpc asset, upload it on [Discord Dev Portal](https://discord.com/developers/applications)

📝 Assets cannot be edited, if you want to change the asset name, you must delete and re-upload the asset to your application

## #2 ┊ Setting up tokens
To use this code, you must have your discord account token, want to know how? Please watch this [video](https://youtu.be/IVZzyjYyUkc)

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
ㅤrpc.getRpcImage(app, "your_asset_name").then(large => {
ㅤㅤsetInterval(() => {
ㅤㅤㅤclient.user.setPresence({
ㅤㅤㅤㅤgame: {
ㅤㅤㅤㅤㅤname: "Discord✨",
ㅤㅤㅤㅤㅤtype: //Choose the type of activity in the form of numbers (https://discord.com/developers/docs/game-sdk/activities#data-models-activitytype-enum)
ㅤㅤㅤㅤ}
ㅤㅤㅤ})
ㅤㅤ}, 16000)
ㅤ})
});
```
