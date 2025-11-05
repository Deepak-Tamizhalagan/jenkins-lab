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

