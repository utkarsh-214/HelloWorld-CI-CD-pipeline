# HelloWorld-CI-CD-pipeline
Basic helloworld project deployment on jenkins  

## Setup For project        
### Step 1
install all the required libraries for python using
```pip install -r requirements.txt```

### Step 2 
go on port 8000 to test the running application

## Setup for connecting github and jenkins 
### Step 1 
get the personal access token(classic) from github
![/token](screenshots/token.PNG?raw=true)

### Step 2 
install the git server plugin from "plugins > available plugins" search git server and install it.

### Step 3
use the personal access token to configure github connection on jenkins, by going to "manage Jenkins > Configure > git", add a new github server and create a new jenkins credential of secret text. Paste the personal access token in the secret column.
![/token](screenshots/jenkins_github.PNG?raw=true)

## Setup for Jenkins build
### Step 1
go to the jenkins dashboard to create a new build and while configuring select git for source 
![/token](screenshots/gitrepo.PNG?raw=true)

### Step 2
now setup the batch script for windows or otherwise shell script for linux or mac system. Here batch script is used as I have a windows system. 
```docker build . -t helloworld```
```docker run -p 8000:8000 -d helloworld```
![/token](screenshots/batch.PNG?raw=true)

Now click on save

### Step 3 
Turn on your docker to make a docker image and container for build and then build the application. Now go to localhost:8000 and check the working of your application
![/token](screenshots/docker.PNG?raw=true)

