## Dev environment for NodeJS Sample App

### Intro

- This is a guide to clone and provision a nodeJS sample app.

Pre-requisites
 
- Git
- Vagrant
- VirtualBox
- Starter code
### Steps

1. Clone the starter code.

2. Configure the Vagrantfile to provision a private network and assign aliases: config.vm.network "private_network", ip: "192.168.10.100" config.vm.hostname = "www.testing.de" config.hostsupdater.aliases = ["development.local"]

3. Sync the app folder on the local host with the virtual machine using the commmand: config.vm.synced_folder"app", "/app"

4. Create a bash script to run commands to install relevant files. This will be titled provision.sh

5. Within the provision.sh file, write out the commands which will install the required files. `#!/bin/bash

6. sudo apt-get update sudo apt-get upgrade sudo apt-get install nginx -y sudo apt-get install nodejs -y sudo apt-get install npm -y sudo npm install pm2 6. Configure the Vagrantfile to execute the provision.sh file. Use the following code config.vm.provision "shell",path: "environment/provision.sh"7. Run the commandvagrant upto get the virtual machine running. 8. Confirm the virtual machine is running using VirtualBox. 9. Login to the virtual machine usingvagrant ssh10. Inside the virtual machine navigate to the app folder usingcd /app/` 11. Clone the app using the commands. This should display the message that the app is ready and listening on port 3000
```
npm install
npm start
```
Access the app on port 3000 i.e www.testing.de:3000 This should display the Sparta logo.
Check the fibonacci url is working i.e www.testing.de:3000/fibonacci/{index}. This should return the number at the specified index according to fibonacci scale.
