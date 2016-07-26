Autodesk Print Manager
===========

Print Manager is a desktop utility which identifies and connects 3D printers and converts files for delivery to a particular model of 3D printer. The utility is used by Print Studio.

On supported 3D printers, Print Manager converts a set of native 3D printer commands into a format recognized by the supported printer models, allowing a "printable" file to be sent to a specific printer model.

<b>To see full documentation of print-manager and download print studio, please request access to the developers' portal at
 <a href="https://spark.autodesk.com/developers/" target="_blank">https://spark.autodesk.com/developers/</a>.</b>
 
This repository has further information on the developers' portal at [Print Studio](https://spark.autodesk.com/developers/showcase/d0716b0d-5cb4-4959-9f10-032be8591c2a). 
If you are a printer manufacturer interested in integrating your printer with Print Manager then see [this guide](https://spark.autodesk.com/developers/reference/printer-manufacturers/integrate-your-printer/integrate-your-printer-model).

For Print Manager to start you must download the geometry processor that is attached to the releases see [Print Manager Releases](https://github.com/spark3dp/print-manager/releases)

When unzipped please edit the localConfig.json file to use this.


## Quick Install Node.js  

   To install on Debian 8 with OctoPrint:
   
  Step 1 - Update your system
  ```
  sudo apt-get update
  sudo apt-get install git-core curl build-essential openssl libssl-dev
  ```
  Step 2 - Install Node.js
   First, clone the Node.js repository:
  ```
  git clone https://github.com/joyent/node.git
  cd node
  ```
  Now, select the specific version of Node needed by Print Manager:
  ```
  git tag # Gives you a list of released versions
  git checkout v0.11.16
  ```
  Then compile and install Node like this:
  ```
  ./configure
  sudo make
  sudo make install
  ```
  Then, check if node was installed correctly:
  ```
  node -v
  ```
  Step 3 - Install NPM
   Simply run the NPM install script:
  ```
  curl https://npmjs.org/install.sh | sudo sh
  ```
  And then check it works:
  ```
  npm -v
  ```
  
  If npm is giving you problems, this is my current fix:
  ```
  npm install -g n
  npm install npm -g
  ```
###Install RoopaServer
Install this in the user directory - all RoopaServer functions are currently tied to this path!
```
cd~
wget https://github.com/spark3dp/print-manager/releases/download/1.5.1/RoopaServer-0d221eaLinux.tar.gz
tar -xzvf RoopaServer-0d221eaLinux.tar.gz
```
###Clone Spark Repo
Clone the Spark printer-manager repo.
```
git clone https://github.com/Robo3D/print-manager.git
cd print-manager/
```

Run: ```npm install``` to install node modules

Create localConfig.json containing: 
```
cd spark-print-mgr
sudo nano localConfig.json
{ "roopaServerPath" : "/home/pi/bin/RoopaServer" }
```
Start server with ```node server.js```
(will start server on localhost:9998)  

Go to: http://localhost:9998/printdb/printertypes to see normal execution

If you see any issues please use the github issue mechanism. 
 
And if you've reached this far without any errors, give yourself a pat on the back. 
