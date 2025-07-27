🗓️ Day 1 – Jenkins Essentials & Setup

🎯 Goal: Understand what Jenkins is and set up a working environment.

🧠 Learn (Theory):
- What is Jenkins? Why Jenkins?
- Jenkins architecture (Master-Agent model)
- Installation (Local/Docker/Cloud-based)

🛠️ Hands-on:
- Installed Jenkins via Docker
- Explored Jenkins UI
- Installed essential plugins (Git, Pipeline, Blue Ocean)

✅ Checkpoint Achieved:
- Jenkins up and running
- Sample Freestyle Job created


🔍 What I Learned Today:
1. What CI/CD is and how it improves development workflows.
    CI (Continuous Integration): Automatically test and merge code changes into the main branch frequently.
    CD (Continuous Delivery/Deployment):
    Delivery: Automatically prepares code for release.
    Deployment: Automatically deploys the code to production.
    👉 Purpose: Faster development, early bug detection, smoother releases.

2. Role of Jenkins in automating builds & deployments.
    Jenkins automates the CI/CD pipeline. It:
    Monitors Git repo for changes
    Builds, tests, and deploys code
    Supports plugins for almost every tool (Docker, AWS, etc.)
    Can scale with agents

3. Production-level CI/CD alternatives to Jenkins (GitHub Actions, GitLab CI, CircleCI).
    | Tool                 | Key Feature                              |
    | -------------------- | ---------------------------------------- |
    | **GitHub Actions**   | Integrated with GitHub; simple workflows |
    | **GitLab CI/CD**     | Built into GitLab; great for DevOps      |
    | **CircleCI**         | Easy cloud-based CI/CD                   |
    | **Travis CI**        | Lightweight; used with GitHub            |
    | **TeamCity**         | Powerful but requires setup              |
    | **AWS CodePipeline** | Integrated with AWS services             |


4. Jenkins setup using Docker & managing Docker volumes.
    Docker volumns helps in saving your work

    docker network create jenkins

    docker volume create jenkins_home

    docker run -d \
    --name jenkins-master \
    --network jenkins \
    -p 8080:8080 -p 50000:50000 \
    -v jenkins_home:/var/jenkins_home \
    jenkins/jenkins:lts


5. Creating and running Freestyle Jobs in Jenkins.
    Go to Jenkins UI → New Item
    Enter name → Select Freestyle Project
    In the job config:

    Source Code Management: Add Git repo
    Build Triggers: E.g., poll SCM, webhook
    Build Steps: Add Shell script or command
    echo "Building project..."
    Save & click Build Now


6. Installing and managing Jenkins plugins.

    Jenkins UI → Manage Jenkins
    Click Manage Plugins
    Under Available tab, search and install plugins
    Examples:
    Docker
    GitHub Integration
    Pipeline
    Restart Jenkins if required

