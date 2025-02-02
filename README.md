## Prerequisites

1. Open port 8000 from your instance's inbound rule (security group) of the server
2. Docker is installed and running on your server. 
3. Docker-compose is installed on the path where you have written/created/kept the docker-compose.yml file.

## Follow below steps in Jenkins for this project -

1. Create a new project in Jenkins and add a brief instruction about the project.
2. Add the GitHub URL of this project in the 'Source Code Management' section.
3. Select 'GitHub hook trigger for GITScm polling' in 'Build Triggers' section.
4. Add the below build steps to start the container and save the project.
   
     ```
     docker-compose up -d
     ```

## Follow below steps in GitHub for this project -

1. Go to the settings of this project and in the Webhooks section, Click on 'Add webhook'.
2. In the payload URL, add the public IP address with the port on which you are accessing Jenkins and 'github-webhook/'.
So, it will look like 'http://54.208.36.209:8080/github-webhook/'.
3. Select 'application/json' in Content Type and select 'Just the push event' in next option and then, click on 'Add webhook'.
Now, make any changes in this project and commit them.
4. In Jenkins, that one build will be created after you commit. So, GitHub webhooks are used to trigger a build in Jenkins whenever someone commits to the project if we select 'Just the push event'.
