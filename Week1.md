
 # WEEK 0 and WEEK 1
 
 ## Create IBM Cloud account
 
 1. To create an IBM cloud account, go to https://cloud.ibm.com/registration
 2. Type in your email and choose a password and click next.
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/account-information.png" width="60%" height="60%">
 
 3. Check your email inbox for the verification code, type it to the field and click next.
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/email-verification-code.png" width="60%" height="60%">
 
 4. Enter your personal information and click next.
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/personal-information.png" width="60%" height="60%">
 
 5. Verify your information and click create account.
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/create-account.png" width="60%" height="60%">
 
 6. Read and acknowledge the policies. Click proceed.
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/acknowledgement.png" width="60%" height="60%">
 
 After account creation, you should land on the cloud dashboard page. on this page you can view and access all ibm cloud resources that you have created or that you are collaborating in. 
- Send the email address that you used to sign in to IBM Cloud to Eelia Mastosalo in Slack.
- At this point, wait until the workshop instructors have invited you to collaborate in the IBM Forum helsinki workspace in IBM Cloud. After the instructors have invited you, proceed to the next step.
 
 ## Accessing the workshop OpenShift cluster
 
 1. On your cloud dashboard, click your account name on the right top corner and choose "IBM Forum Helsinki".
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/cloud-dashboard.png" width="60%" height="60%">
 
 2. When you have succesfully switched to the IBM Forum helsinki dashboard, you should see one cluster resource available to you on the left hand side of the dashboard. Click the "Clusters" link.
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/open-clusters.png" width="60%" height="60%">

 3. On the resources page, click on the "ocp43-workshop"
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/open-workshop.png" width="60%" height="60%">

 4. You should land on the ocp43-workshop dashboard page. Your account may not have sufficient credentials to view the cluster statuses on the right hand side nor the logging and monitoring components but dont worry, those are not needed for this workshop. 
 - Click on the blue "OpenShift Web Console" button on the right top corner of the dashbord. 
 - Opening the openshift web console trough this link is necessary only once. This is because clicking the link triggers a script that automatically creates a useraccount for you in openshift. Afterwards you can just bookmark the openshift web console address and open it straight up without going trough the ibm cloud. 
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/ocp-workshop-ibm-cloud.png" width="60%" height="60%">

 5. Now you should land on the OpenShift Web Console Dashboard page. Dont worry if you are not able to see the cluster nodes, details, status, activity or events. The account that is automatically created for you has only "edit" rights for now and thus is not sufficient to view the cluster in more detail.
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/ocp-dashboard.png" width="60%" height="60%">



Now that you have access to the cluster through the interface, it’s time to learn how to do the same things through the command line. However, first you need to install the CLI to be able to give **oc** commands from the terminal. Select your operating system and follow that instructions to install CLI.

## Install the OpenShift CLI (oc)

1. Click on the **question mark** at the top right
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/Questionmark.png" width="60%" height="60%">
 
2. From the drop-down menu click on **Command Line Tool**
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/list.png" width="20%" height="20%">
 
3. Scroll down the page until you see **oc - OpenShift Command Line Interface (CLI)**
<img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/Command-line-tool-logged-in.png" width="60%" height="60%">

4. Download and install the oc for your operating system.

* unzip (windows) or untar (linux/mac) the archive and run the executable.

## Logging in to the CLI

After installing CLI let's log in to the OpenShift cluster through the terminal.
 
1. On the same **Command line tools** page, click on the **Copy Login Command**
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/Command-line-tool-logged-in.png" width="60%" height="60%">
 
2. Click on the **Display token**
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/Display-token.png" width="20%" height="20%">

3. Under **Log in with this token** copy the command and paste it to the terminal.
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/token-view.png" width="60%" height="60%">

You should see the text: 
<img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/Terminal.png" width="60%" height="60%">

You are now succesfully logged in to the cluster. Congratulations!
 
## Managing projects

1. At this point, Slack Eelia Mastosalo that you have gotten to this part of the workshop and wait until the instructors assing more privileges for your openshift user. The new role that you will get is called "self-provisioner". The privileges of "self-provisioner" are the same as your original "edit" role but with the added rights to create, edit and delete your own openshift projects.
- After you have been assigned as "self-provisioner", continue to the next step.
- You can read more about the default roles and privileges here: https://docs.openshift.com/container-platform/4.3/authentication/using-rbac.html

2. From the OpenShift dashboard page, click open the home menu on the lefthand side of the page and click "projects". The projects page opens. Click "Create project" on the left top side of the page to create a new project.
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/projects-page.png" width="60%" height="60%">
 
3. Create a new project and name it "projectname-myname". you can decide the project name yourself, a good example is "mk-week1-myname". replace myname with your name to identify your own project workspace.
- The project name must consist of lower case alphanumeric characters or '-', and must start and end with an alphanumeric character.
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/create-project.png" width="60%" height="60%">
 
4. After the creation of the new project, you will land on the project dashboard page. This project will work as your own workspace for this workshop.
- Resources in projects are isolated from other projects by default.
 <img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/project-dashboard.png" width="60%" height="60%">
 
5. Next try to create a project from the command line. If you are not already logged in to the cluster CLI, login now using the instructions from the part "Logging in to the CLI". After a succesfull login you can create a new project by running a command:
- _oc new-project mk-cli-test-myname_
- After a succesfull project creation, the new project is automatically set as your default project.

6. Next it is time to delete the project that your just created. Run the following command on the CLI to delete the project.
- _oc delete project mk-cli-test-myname_
 
 
## Deploying a test application

As the final part of the Week 1 challenge, you will deploy a snake game running in a docker container.

1. On the OpenShift dashboard. Click the **Administrator** on the left upper corner and choose **Developer**
<img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/game-developer.png" width="60%" height="60%">

2. On the Topology page, make sure to choose your own project from the project pulldown menu on the top left of the Topology page. 
<img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/game-project-choose.png" width="60%" height="60%">

3. After you are in your own project space, click the **Container Image** button.
<img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/game-from-container.png" width="60%" height="60%">

4. Type **aschil/snake** to the image field name and hit enter. This will automatically fetch the snake container from aschil public docker repository.
<img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/game-image-name.png" width="60%" height="60%">

5. Scroll down the page to review the options. The General and Resources fields are automatically filled. Make sure that in the Advanced Options, the box **Create a route to the application** is checked. Then hit Create.
- By checking the checkbox, service and route is automatically created for your application.
- Service exposes the application interface from inside the container.
- Route exposes the application interface to the internet so that it can be accessed online.
- You will learn more about services and routes and how to create them manually in weeks 2 and 3.
<img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/game-image-name.png" width="60%" height="60%">

6. After hitting create, you will land back on the Topology page, now with your snake game visible in the topology of your project. If you click on your snake game, a window will open to the right side of the screen. From there you can view the containers starting. 
- First an init container will start and initialize the snake container.
- When the init container finishes and exits, the snake game container will start.
- When the snake container is running, you will find the automatically created route to your application on the bottom part of the window.
- Click the route link to access your application and enjoy the game.

<img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/game-created.png" width="60%" height="60%">

## Delete your application

When you are done with your new and shiny snake application, remember to delete it to save resources in our openshift cluster. Go to the projects view, find your project on the list and click on the three dots on the right beside your project name and click delete.
<img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/project-delete.png" width="100%" height="100%">

You are then asked to type in the name of your project to confirm that you really want to delete it. Type it and click delete.
<img src="https://raw.githubusercontent.com/jaanae/devops-workshop/master/delete-project.png" width="60%" height="60%">

## You have now completed Week 1!






