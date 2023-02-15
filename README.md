# The Interlock Universal Access NFT Demonstration Application:

<img style="top: -10px" align="right" width="150" height="150" src="https://user-images.githubusercontent.com/69293813/211382026-cf3fc80c-4489-4017-b10e-c1cb27c89ae0.png">
<img align="right" width="100" height="100" src="https://user-images.githubusercontent.com/69293813/211380333-f29cd213-f1f5-46c6-8c02-5ba0e15588f0.png">

THIS DOC IS CRUDE, NOT INTENDED FOR FINAL RELEASE.

This is a test repo for the purpose of putting together a seamless demonstration of the Aleph Zero Interlock grant minestone 2 product.

This contains instructions for how to fire up the NFT authentication server, the restricted access area server, and the client application, after cloning from a demo repo.

Please see if this works (o Interlock friends) and provide feedback. The target audience for this experience include people who do not necessarily have much experiece working with terminals/troubleshooting. This is why the node modules are included.

## Preparation instructions:

Open up your terminal.

### (1)

You need git first. Make sure you have it.

##### mac

```
brew install git
```
or
##### most linux

```
sudo apt install git
```

### (2)

Now you need to make sure you have node.js

##### mac

```
brew install node
```
or
##### most linux

```
sudo apt install nodejs
```

### (3)

Now clone this demo repo to your computer and navigate to it.

```
git clone https://github.com/interlock-network/UA-NFT-DEMO-APP;
cd UA-NFT-DEMO-APP
```

## Run the demo.

We need to spin up two servers, and one client application.

### (1) - AUTH-SERVER

Start up the NFT authentication and credential registration server. This server in practice will be controlled and administrated by the authority issuing universal access NFTs. This server never sees access credentials in cleartext form. Run:

```
node CLIdemo/serverMain.js
```

### (2) - RESTRICTED-AREA-SERVER

Create a new terminal instance in a new tab, making sure it is in the same directory. Start up the restricted access area server. This server is responsible for receiving access credentials over https connection and verifying that their hashes match the hashes stored on the blockchain during the NFT authentication and credential registration process. This resitricted access area server serves content that only verified universal access NFT holders have access to. In practice, this server could serve the entire service, or it may simply issue an authentication token for proffer elsewhere. Run:

```
node --expose-gc CLIdemo/restrictedArea.js
```

### (3) - CLIENT-APP

Finally we can start up the client application. Create a new terminal instance in the same directory, and place it side-by-side the two server terminals if you want to soak in all the play-by-play action at once. Run:

```
node CLIdemo/clientMain.js
```

Ando go from there.

## Play with the app.

There you have it. This app points to an instance of the NFT smart contract that I use on blockchain for testing purposes. For server owner blockchain credentials, I include a throw away test account. Likewise, for client signing credentials, I include a throw away client test account. You have the option to use your own account though if you please.

## Break the demo.

Please.
