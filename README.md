# Blockless Bless Network Bot 

## Description
This script automates network or node operations for Blockless Bless Network.

## Features
- **Automated node interaction**
- **Multi account**
- **Multi NodeID**
- **Proxy support**

## Prerequisites
- [Node.js](https://nodejs.org/) (version 12 or higher)

## Installation

1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/recitativonika/blockless-bless-network-bot.git
   ```
2. Navigate to the project directory:
   ```bash
   cd blockless-bless-network-bot
   ```
4. Install the necessary dependencies:
   ```bash
   npm install
   ```

## Usage
1. Register to blockless bless network account first, if you dont have you can register [here](https://bless.network/dashboard?ref=84PLBS).
2. Set and Modify `config.js`. Below how to setup this file. Put your `B7S_AUTH_TOKEN (usertoken)`, `nodeid` and `hardwareid` in the file. Below how to get it:
3. To get your `token/usertoken`, follow this step:
	- Login to your bless account in `https://bless.network/dashboard`, make sure you is in this link (dashboard) before go to next step
	- Go to inspect element, press F12 or right-click then pick inspect element in your browser
	- Go to application tab - look for Local Storage in storage list -> click `https://bless.network` and you will see your B7S_AUTH_TOKEN.
	- or you can go Console tab and paste this 
	```bash
	localStorage.getItem('B7S_AUTH_TOKEN')
	```
4. To get your `nodeid` and `hardwareid`, follow this step:
	- Download the [extension](https://chromewebstore.google.com/detail/bless/pljbjcehnhcnofmkdbjolghdcjnmekia)
	- after you download the extension, open `chrome://extensions/?id=pljbjcehnhcnofmkdbjolghdcjnmekia`
  	- Enable `Developer mode` in top right, then press `service worker`, or you can right click the extension windows and use `inspect/inspect element` too. You will see new tab open.
  	![image](https://github.com/user-attachments/assets/63151405-cd49-4dff-9eec-a787a9aa3144)
	- Go to `network` tab, then open the `Bless extension` and login to your account.
  	- After you login to your account, search name with your pubkey (example : `12D3xxxx`), open and copy the `pubkey` and `hardwareid`
	![image](https://github.com/user-attachments/assets/70bcb0c6-9c47-4c81-9bf4-a55ab912fba6)

5. **~~Or you can use `gen.js` and run with this to get NodeID and HardwareID~~** *Only work for generate HardwareID*
	```bash
 	node gen.js
 	```
6. If you want to use `proxy`, you can add in the config file for each nodeid.
7. Put all data of `usertoken`, `nodeid` and `hardwareid` in the `config.js`, it will look like this:
	```bash
	module.exports = [
	    {
	        usertoken: 'usertoken1',
	        nodes: [
	            { nodeId: 'nodeid(pubkey)1', hardwareId: 'hardwareid1', proxy: 'proxy1' },
	            { nodeId: 'nodeid(pubkey)2', hardwareId: 'hardwareid2', proxy: 'proxy2' },
	            { nodeId: 'nodeid(pubkey)3', hardwareId: 'hardwareid3', proxy: 'proxy3' },
	            { nodeId: 'nodeid(pubkey)4', hardwareId: 'hardwareid4', proxy: 'proxy4' },
	            { nodeId: 'nodeid(pubkey)5', hardwareId: 'hardwareid5', proxy: 'proxy5' }
	        ]
	    },
	    {
	        usertoken: 'usertoken2',
	        nodes: [
	            { nodeId: 'nodeid(pubkey)6', hardwareId: 'hardwareid6', proxy: 'proxy6' }
	        ]
	    }
	    // Add more usertokens as needed
	];
	```

5. Run the script:
	```bash
	node index.js
	```
***NOTE:***
- **The total time is refreshed every 10minute connection, One account only can have 5 nodeid connected, I recomended to save your Nodeid(pubkey) and hardwareid of your account**
- **Your hardwareinfo data of the nodeid is saved in hardwareInfo.json when you running the script, please do not delete this file. If you add more nodeid or accounts, it will automatically add the data when you start the script**

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Note
This script only for testing purpose, using this script might violates ToS and may get your account permanently banned.

My reff code if you want to use :) : 
https://bless.network/dashboard?ref=84PLBS
