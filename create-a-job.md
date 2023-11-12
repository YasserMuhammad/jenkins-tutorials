# Jenkins Job for Deploying Angular Project - The Fun Way 🚀

## Introduction

This guide provides step-by-step instructions on setting up a Jenkins job to deploy an Angular project. Jenkins is a popular open-source automation server that can be used for continuous integration and continuous deployment (CI/CD).

![Step 1](https://media.giphy.com/media/26xBwdIuRJiAIqHwA/giphy.gif)

### Prerequisites

Before you begin, ensure that the following prerequisites are met:

1. Jenkins is installed and running.
2. Node.js and npm are installed on the Jenkins server.
3. Angular CLI is installed globally (`npm install -g @angular/cli`).

## Step-by-Step Guide

### 1. **Create a New Jenkins Job**

- Open Jenkins and navigate to the dashboard.
- Click on "New Item" to create a new job.
- Enter a name for the job (e.g., "Angular_Deploy") and choose "Freestyle project."

### 2. **Configure Source Code Management (SCM)**

- Under the "Source Code Management" section, select your version control system (e.g., Git).
- Enter the repository URL and set up the necessary credentials.

### 3. **Build Triggers**

- Configure build triggers according to your needs. For example, you can trigger the build on SCM changes.

### 4. **Build Environment**

- Add a build step to install Node.js dependencies. In the build section, add an "Execute shell" or "Execute Windows batch command" step:

  ```bash
  npm install
  ```

### 5. **Build**

- Add another build step to build the Angular project:

  ```bash
  ng build --prod
  ```

### 6. **Artifact Archiving**

- In the "Post-build Actions" section, add "Archive the artifacts."
- Specify the files to archive, typically found in the `dist/` directory after an Angular build.

### 7. **Deploy to Server**

- Add a new build step to deploy the artifacts to your server. This might involve copying files to a web server directory or using a deployment tool.

### 8. **Save and Run**

- Save your Jenkins job configuration.
- Manually trigger the build to verify that everything is set up correctly.

### Optional: Integrating with Webhooks

If you want to automate the build process further, consider setting up webhooks to trigger Jenkins builds on repository changes.

## Conclusion

Congratulations! You've successfully set up a Jenkins job to deploy an Angular project. This automated CI/CD process ensures that changes are built, tested, and deployed consistently, improving the efficiency and reliability of your Angular project deployment.
