### Setting Up Vite-App in a Jenkins Pipeline and Dockerized Environment

[Jenkins](https://www.jenkins.io/) is a popular open-source automation server that is widely used for building, testing, and deploying code. If you're working with Node.js applications and want to integrate them into your CI/CD pipeline, you'll need to install Node.js on your Jenkins server and configure it for your pipeline projects.

### Prerequisites to run this project locally

1. Install NodeJS plugin in Jenkins
2. Go to Manage Jenkins > Tool > NodeJS installation
3. Add NodeJS installation and add name as `nodejs` or `anythingyoulike` and select `Install` and select NodeJS version`as you may like and click on`Save`.
4. Create a new `Pipeline` job.
5. In `Build Triggers` select `GitHub hook trigger for GITScm polling` .
6. in Github Set up a webhook in your repository that triggers the Jenkins job whenever there's a push event. To do this, go to your repository's Settings > Webhooks > Add webhook and add the following URL in the Payload URL field: `http://<your-jenkins-server-url>/github-webhook/`. Make sure to replace <your-jenkins-server-url> with your Jenkins server's URL.
7. In `Pipeline` section select `Pipeline script from SCM` and select `Git` in `SCM` and add your repository URL in `Repository URL` and select `Credentials` and add your `Github` credentials and select `Branches to build` as `*/master` on any `branch you like` , Script Path as `Jenkinsfile` and click on `Save`.
   and click on `Save`.
   8.You can manually trigger the build by clicking on `Build Now` or you can push any changes to your repository and it will automatically trigger the build.
