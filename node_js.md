# NODE JS

### Install node js
Official installation instructions: [node.js](https://github.com/nodesource/distributions/blob/master/README.md#installation-instructions)

* Install node js last version.
```shell
curl -fsSL https://deb.nodesource.com/setup_19.x | sudo -E bash -
sudo apt update && sudo apt autoremove -y
sudo apt install -y nodejs
```

* You can install npm last version: `sudo npm install npm@latest -g`. Or choose version: `sudo npm install npm@8.19.2 -g`

### Uninstall node js
```shell
sudo apt remove nodejs -y && sudo apt remove npm -y && sudo apt update
```

### Install pm2
```shell
sudo npm install pm2 -g
```
