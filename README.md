# vagrant-chef-nodejs
## Simple nodejs app using chef and vagrant

#### Step 1: Create vm using 
###### vagrant init ubuntu/trusty64

#### Step 2: Generate cookbook
###### chef generate cookbook mycookbook

#### Step3: Update cookbooks
###### -> cd mycookbook
###### -> Update Berksfile
###### -> berks vendor cookbook

#### Step 4: Update VagrantFile
###### -> Update forwarded_port
###### -> Update synced_folder
###### -> Update recipe

#### Step 5: Provision VM

#### Step 6: Run Node app inside VM
###### -> ssh into VM
###### -> Check node -v
###### -> Check app folder
###### -> cd app 
###### -> node app.js

#### Step 7: From Host check app
###### -> http://localhost:3000

#### Step 8: Change from host
###### -> Change app.js from host
###### -> Restart node app inside VM
###### -> check http://localhost:3000 reflects the change
