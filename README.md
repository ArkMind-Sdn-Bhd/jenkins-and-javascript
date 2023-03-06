# Getting started with Jenkins with GitHub

# Installation of Jenkins
First install the Jenkins in the pc.

Make sure you have installed JAVA jdk 11/17 version in your laptop and set up the JAVA_HOME in your system environment.

Open the Jenkins through http://localhost:8080 and create a user account and login to the Jenkins.

Inside the Jenkins we can create our Jenkins project by clicking on the "+ New Item" button. Select the Freestyle project as our project type.

# Project Configuration of Jenkins
In the General section, click on the "GitHub project" and insert the project url.

Then move to the Source Code Management section, click on the Git and insert the github repository url into the field of Repository URL.

Next in the Built Triggers section, choose the GitHub hook trigger for GITScm polling.

Finally click on the SAVE button.

# Installation of ngrok
Install the ngrok in the pc. link:https://ngrok.com/download. 

Create an account in Ngrok and get the authtoken.

Next run the command ### 'ngrok config add-authtoken <token>' in your terminal.

Next run the command ### 'nrgok http 8080' to create a tunnel.

After executing the command, it should pop up a ngrok terminal which include the informations.

Copy the forwarding address inside the ngrok terminal, the purpose of this address is to insert it inside the Payload URL.

# Configuring the Webhook in GitHub
Go to the Settings in your GitHub repositor and look for the Webhook inside the section of code and automation and click on it.

Next add the webhook by click on the button of Add Webhook.

Then paste the forwarding address inside the field of Payload URL.

Next there are 3 options for us to choose which events would trigger the webhook, choose the option of "send me everything".

Finally click on the button of Add Webhook. 

Now when you push anything to the repo, it would trigger the webhook and Jenkins to start the build as well. 


# Getting started with PM2 and Dotnev
Sometimes we might use a different environment for our project.
In order for us to switch between different environments, we will use DOTENVto define the environment for our project. 
In this task, I was using my backend application (ExpressJS_Handson). 
Create a few commands for different environments in package.json.
 For example such as “ “ “pm2:dev” : “ tsc && pm2 start ecosystem.config.js –env dev” ”, “ “pm2:local” : “ tsc && pm2 start ecosystem.config.js –env local””,  and “ “pm2:test” : “ tsc && pm2 start ecosystem.config.js –env test””. 

 The “—env dev” is actually telling the pm2 which environment to use inside the ecosystem.config.js. Inside the ecosystem.config.js, create the environment variables accordingly. 

Open the command prompt and go to the backend project folder and execute the command of “ npm install dotenv --save “. 
This command will install the DOTENV dependency into the project folder.
 Meanwhile, create a few .env files in the project folder (.env.dev, .env.local, and .env.test). 

 Next, execute the command of “npm run pm2:local”.
  This command is using pm2 to serve the backend application and the environment using it is local.


