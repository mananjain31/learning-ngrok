# Installing ngrok: Share Your HTTP, TCP and Websocket servers with the World!
## Step 1: Initialize Your Project
First things first, let's initialize our project. We'll be using yarn for this tutorial, but feel free to use npm if that's what you're comfortable with.

```bash
yarn init -y

```

## Step 2: Install ngrok
Now that our project is set up, let’s add ngrok to the mix. Run the following command to install ngrok:

```bash
yarn add ngrok
```
## Step 3: Login and get ngrok authtoken
Login to your ngrok account and get your authtoken from https://dashboard.ngrok.com/auth/your-authtoken
## Step 4: Configure ngrok
add ngrok authtoken to your project
```bash
yarn ngrok authtoken <your-authtoken>
```

# Expose Your Local `HTTP Server`
Have you ever wanted to share your local server with someone outside your network? With ngrok, it's easy! Follow these simple steps to get started.

Navigate to the `exposing-local-http` project folder and serve the static files using http-server. This project contains a simple index.html file that will be served by http-server on port 8080.

```bash
yarn http-server .
```

Return to the root of the repository and run ngrok to expose the http-server on port 8080:

```bash
yarn ngrok http 8080
```
Voila! You will receive http and https URLs that you can use to access your local server from anywhere in the world. Share your work with friends, colleagues, or clients in just a few simple steps.

Happy sharing!

# Expose your Local `Websocket Server` or `TCP Server`
Have you ever wanted to share your local websocket server with someone outside your network? With ngrok, it's easy! Follow these simple steps to get started.

Navigate to the `exposing-local-websocket` project folder and serve the static files using http-server. This project contains a simple index.html file that will be served by http-server on port 8080.

```bash
node index.js
```

to test the websocket server, open console in browser and run the following command

```js
(function test(url, message) {
  const ws = new WebSocket(url);
  ws.addEventListener("open", () => {
    ws.onmessage = console.log;
    ws.send(message);
  });
})("ws://localhost:8080", "Hello There!");
```

Return to the root of the repository and run ngrok to expose the websocket-server on port 8080:

```bash
yarn ngrok tcp 8080
```

Voila! You will receive a URL that you can use to access your local websocket server from anywhere in the world. Share your work with friends, colleagues, or clients in just a few simple steps.

to test that the websocket server is working, open console in browser and run the following command

```js
(function test(url, message) {
  const ws = new WebSocket(url);
  ws.addEventListener("open", () => {
    ws.onmessage = console.log;
    ws.send(message);
  });
})("ws://<your-tcp-link-obtained>", "Hello There!");
```
where `<your-tcp-link-obtained>` is the tcp link obtained from ngrok

Happy sharing!
