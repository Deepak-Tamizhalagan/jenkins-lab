# Jenkins CI/CD Pipeline Integration with GitHub
## Project Overview

This project demonstrates the setup and automation of a Continuous Integration (CI) pipeline using Jenkins integrated with GitHub.
The goal was to automatically detect changes in the GitHub repository, trigger a build, run basic test steps, and send build status notifications via email.

## Objectives

+ Integrate Jenkins with a GitHub repository using a Personal Access Token (PAT).

+ Configure a Jenkins pipeline to automatically:

+ Checkout the source code

+ Build the project (simulated build)

+ Run simple test steps

+ Send notification emails on success or failure

+ Implement a polling-based trigger to detect repository changes every few minutes.

## Tools and Technologies

CI/CD Server-	Jenkins 2.528.1

Source Control-	Git & GitHub

Scripting	Groovy- (Jenkinsfile)

Notification-	Gmail SMTP (Email Extension Plugin)

Operating System-	Windows 10

# Pipeline Design
Stages Included

Checkout – Clone the GitHub repository using the configured credentials (github-pat).

Build – Simulate the build process with an echo command.

Test – Run a simple test command (e.g., echo "Running tests").

Notify – Send email notifications for success or failure using Gmail SMTP.

## Trigger Mechanism

Polling-Based Approach:
Jenkins is configured to poll the GitHub repository at regular intervals (every 5 minutes).
When a change is detected (e.g., an updated README or Jenkinsfile), the pipeline is automatically triggered.

Example configuration in Jenkins:

H/5 * * * *


(Runs every 5 minutes)

## Testing and Verification

Made a small change in the repository (e.g., edited README).

Jenkins automatically detected the change through pollSCM and triggered a build.

Verified all pipeline stages executed successfully:

✅ Checkout

✅ Build

<img width="1433" height="785" alt="image" src="https://github.com/user-attachments/assets/939f7123-4037-43bd-9291-0c6c241e338a" />
<img width="1918" height="786" alt="image" src="https://github.com/user-attachments/assets/2c67e735-defc-41e6-b6b2-d1f20fb8c9dd" />



✅ Test

✅ Notification

<img width="1603" height="777" alt="image" src="https://github.com/user-attachments/assets/83f9c8d1-bce9-4406-9356-34f62be061fe" />



## Results

Jenkins successfully automated the build pipeline for the GitHub project.

The pipeline accurately triggered on new commits.

Email notifications were received for both successful and failed builds.

The setup demonstrates the core DevOps CI/CD principle — continuous integration and feedback.


