🗓️ Day 6 Notes – Jenkins RBAC, Credentials, Shared Libraries & Django CI/CD
🎯 Goal: Secure Jenkins pipeline with real-world deployment using Docker & Django

🧠 Learn (Theory):
1. Credentials Masking in Jenkins:
    -Used withCredentials block to securely inject and mask secrets like tokens, usernames, and passwords.
    -Prevents credentials from being exposed in logs.


    withCredentials([string(credentialsId: 'my-secret', variable: 'TOKEN')]) {
        sh 'echo $TOKEN'
    }

2. RBAC (Role-Based Access Control):
    - Installed Role Strategy Plugin.
    - Created roles and assigned permissions:
        -Admins: Full access
        -Developers: Job-level access
        -Viewers: Read-only

    -Controlled access by users/groups efficiently.

3. Jenkinsfile for Django App Deployment:
    -Created a full CI/CD pipeline using a Jenkinsfile:
        -Clone → Build → Test → Docker Build → Docker Compose Deploy

4. Docker + Docker Compose Deployment:
    -Built a Django app image using a custom Dockerfile.
    -Used docker-compose.yml to manage services and deploy containers.

5. Shared Libraries in Jenkins:
    -Created reusable logic using shared libraries.
    -Structure:

            vars/
                docker_build.groovy
                docker_push.groovy

    -Called methods from library in Jenkinsfile for DRY (Don't Repeat Yourself) practices.

6. Jenkins Best Practices:
    -Avoid exposing secrets in strings ("echo $SECRET" ✅ vs 'echo $SECRET' ❌).
    -Use declarative syntax for readability.
    -Centralize logic with shared libraries.
    -Always use withCredentials for handling sensitive data.


🛠️ Hands-on:
✅ Pipeline created to:
    -Build Django app
    -Build Docker image
    -Push to DockerHub
    -Deploy via Docker Compose

✅ Role-based access configured
✅ Shared libraries integrated

🔗 Useful Links:
Django App Repo: github.com/swastik-git/django-notes-app
Docker Image: DockerHub - sd-django-app
Shared Library Code: github.com/swastik-git/jenkins-shared-libraries
Jenkins Notes Repo: github.com/swastik-git/kickstart_jenkins
blog and docs - 
    1. https://www.jenkins.io/doc/book/pipeline/jenkinsfile/#string-interpolation
    2. https://www.jenkins.io/doc/pipeline/steps/credentials-binding/
    