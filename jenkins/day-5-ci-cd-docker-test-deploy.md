📘 Day 5 Notes – CI/CD Integration with Docker + Testing + Deploy
🗓️ Day 5 – CI/CD Integration: Docker + Test + Deploy
🎯 Goal: Use Jenkins for a real-world CI/CD pipeline with Docker and deployment steps

🧠 Learn (Theory):
1. Docker in Jenkins
    -Build Docker images inside Jenkins pipeline
    -Push image to DockerHub or private registry
    -Use credentials plugin for authentication

2. CI Testing Best Practices
    -Unit tests: Validate small components
    -Linting: Maintain code quality
    -Integration tests: Test module communication

3. Deployment Options
    -Deploy via SSH to test/staging/prod servers
    -Use dummy .sh scripts to simulate deployment
    -Real-world: EC2, Kubernetes, or serverless deployments

🛠️ Hands-on Implementation:
✅ Docker Build Step:
    sh 'docker build -t yourname/app:${BUILD_NUMBER} .'


✅ Docker Push:
    withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'USER', passwordVariable: 'PASS')]) {
        sh "docker login -u $USER -p $PASS"
        sh 'docker push yourname/app:${BUILD_NUMBER}'
    }

✅ CI Testing Stage:
    stage('Test') {
    steps {
        sh 'npm install'
        sh 'npm run lint'
        sh 'npm test'
    }
    }
✅ Deployment Stage (Simulated with .sh script):
    stage('Deploy') {
    steps {
        sshagent(['server-ssh-creds']) {
        sh 'ssh user@server "bash -s" < deploy.sh'
        }
    }
    }
✅ Checkpoint Achieved:
- Jenkins pipeline now:
    -Builds Docker image
    -Pushes it to DockerHub
    -Runs unit, lint, and integration tests
    -Deploys the app via SSH script