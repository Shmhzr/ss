gthub to ec2
strt ec2 srvr
ntwrk sttngs> allw - ssh,https,http
security> seqrty grps(edit inbound rules)> add rule> customtcp 4000,0.0.0.0/0
goto bitvise
login to ec2 srvr
update, upgrade, nginx
curl -SL https://deb.nodesource.com/setup_16.x|sudo -E bash
install nodejs
git clone <repo link>
cd repo folder
npm install
node index.js
cp ip, add :4000

cd prjct_fldr
git init
git add .
git commit -m "Initial commit"
Create a new repository on GitHub
git remote add origin <repo link>
git push -u origin master/main
git clone <repo link>
cd clned fldr




#!/bin/bash
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install -y nginx
systemctl start nginx
systemctl enable nginx
sudo apt-get -install -y git
curl -SL https://deb.nodesource.com/setup_16.x|sudo -E bash
sudo apt-get install nodejs
git clone <repository link>
cd repository_name
npm install 
node index.js





cd /
cd etc
cd nginx
cd sites-available
sudo chmod 777 default
sudo nano default

proxy_pass http://localhost:4000;
proxy_http_version 1.1;
proxy_set_header Upgrade $http_upgrade;
proxy_set_header Connection 'upgrade';
proxy_set_header Host $host;
proxy_cache_bypass $http_upgrade;
