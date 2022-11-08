# Creating a Jenkins pipeline

## Create the pipeline project

Focus on the Jenkins website. Click "New Item" at the top left.

![Image 16](./assets/16.png)

In the "Enter an item name" field, specify the name for your new Pipeline project (e.g. myflaskapp_pipeline). Scroll down and click "Pipeline". Click OK at the end of the page.

![Image 17](./assets/17.png)

Click the "Pipeline" tab at the top of the page.

![Image 18](./assets/18.png)

From the Definition field, choose the "Pipeline script from SCM" option. This option instructs Jenkins to obtain your Pipeline from Source Control Management (SCM), which will be your locally cloned Git repository. From the SCM field, choose "Git".

In the "Repository URL" field, specify the URL of your git repository:
https://github.com/<YOUR-GITHUB-ACCOUNT-NAME>/<YOUR REPOS NAME> 
where <YOUR-GITHUB-ACCOUNT-NAME> and <YOUR REPOS NAME> is your Github account name and repository name respectively. 
  
![Image 19](./assets/19.png)

Also, change "Branch Specifier" field to `*/main`.

![Image 20](./assets/20.png)

The script path parameter defines that the stages and steps in the pipeline are defined "Jenkinsfile" in the Git repository. 

Refer to the following as an example Jenkinsfile.

![Image 21](./assets/21.png)

The pipeline consists of two stages:
1. Build Stage: Setup / activate the Python virtual environment and install the dependencies (the required Python libraries are specified in requirements.txt).

![Image 22](./assets/22.png)

2. Test Stage: Execute the unit tests which are defined in "application_test.py". The test results are output as junit-xml format. The post step is for asking the Jenkins to archive the test results.

Click "Save" to save your new Pipeline project.

<br/>