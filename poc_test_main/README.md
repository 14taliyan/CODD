
Jenkins Pipeline for python flask based application using  SonarQube, Argo CD, Helm and Kubernetes.
Note : for terraform deatils please check terraform_my_aks README
Note : for application please check poc_test README 


Jenkins : for continous integration 
Argo CD : for continous deployment

STEPS:
Prerequisites:

Python flask application code hosted on a Git repository
Docker 
Jenkins server
Kubernetes cluster
Helm package manager
Argo CD

STEPS:
1. Install the necessary Jenkins plugins:
   1.1 Git plugin or configure with webhooks
   1.2 Pipeline plugin
   1.3 Kubernetes Continuous Deploy plugin

2.  Jenkins pipeline:
   2.1 Configure Jenkins with git Repository by webhook 
       for continous integration.
   OR 
   2.2 use plugin    

3. Define the pipeline stages:
    Stage 1: Checkout the source code from Git.
    Stage 2: Build the python flask app using docker.
    Stage 3: Run SonarQube analysis to check the code quality.
    Stage 4: Deploy the application to a test environment using Helm.
    Stage 5: Run user acceptance tests on the deployed application.
    Stage 6: Promote the application to a production environment using Argo CD.

4. Configure Jenkins pipeline stages:
    Stage 1: Use the Git plugin to check out the source code from the Git repository.
    Stage 2: build application using docker
    Stage 3: Use the SonarQube plugin to analyze the code quality of the  application.
    Stage 4: Use the Kubernetes Continuous Deploy plugin to deploy the application to a test environment using Helm.
    Stage 7: can also  Use a testing framework like Selenium to run user acceptance tests on the deployed application.
    Stage 8: Use Argo CD to promote the application to a production environment.

5. Set up Argo CD:
    Install Argo CD on the Kubernetes cluster using operator or helm.
    my-aks-charts Helm chart for the  application that includes the Kubernetes manifests and Helm values.
    Set up a Git repository for Argo CD to track the changes in the my-aks- charts and Kubernetes manifests.
    Argo CD is tracking changes between my-aks-charts and kubernetes and update states automatically.

6. Configure Jenkins pipeline to integrate with Argo CD:
   6.1 Add the Argo CD API token to Jenkins credentials.
   6.2 Update the Jenkins pipeline to include the Argo CD deployment stage.

