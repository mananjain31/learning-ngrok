# Installing ngrok: Share Your Local Server with the World!

Have you ever wanted to share your local server with someone outside your network? With ngrok, it's easy! Follow these simple steps to get started.

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

# Step 3: Login and get ngrok authtoken
Login to your ngrok account and get your authtoken from https://dashboard.ngrok.com/auth/your-authtoken

# Step 4: Configure ngrok
add ngrok authtoken to your project

```bash
yarn ngrok authtoken <your-authtoken>
```

### Step 5: Expose Your Local HTTP Server
Navigate to the “exposing-local-http” project folder and serve the static files using http-server. This project contains a simple index.html file that will be served by http-server on port 8000.

```bash
yarn http-server .
```

Return to the root of the repository and run ngrok to expose the http-server on port 8080:

```bash
yarn ngrok http 8080
```
Voila! You will receive http and https URLs that you can use to access your local server from anywhere in the world. Share your work with friends, colleagues, or clients in just a few simple steps.

Happy sharing!