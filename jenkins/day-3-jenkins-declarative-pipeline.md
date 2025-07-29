🗓️ Day 3 – Pipelines (Declarative Syntax)
🎯 Goal: Understand and implement your first Jenkinsfile using declarative pipeline syntax.

🧠 Learn (Theory):
-What is a Jenkinsfile and why it matters
-Declarative syntax structure vs scripted pipelines
-Key blocks in a Jenkins pipeline:
-pipeline, agent, stages, steps, post, environment
-Using environment variables in a pipeline
-Handling post-build actions like always, success, failure

🛠️ Hands-on:
-Created a Pipeline Job in Jenkins
-Pulled Jenkinsfile from a GitHub repo
-Defined stages:
    Clone the repo
    Build using npm install
    Test using npm test
-Added post section to log success or failure
-Used environment variables inside the pipeline

✅ Checkpoint Achieved:
-Jenkins successfully fetched and executed a Jenkinsfile from GitHub
-All pipeline stages working as expected
-Understood and used each declarative block with confidence

🔍 What I Learned Today:
1. Jenkinsfile (Declarative Syntax)
    A Jenkinsfile defines CI/CD pipelines as code. Declarative syntax is simpler, more readable, and structured.
    Basic structure:

pipeline {
  agent any
  environment {
    NODE_ENV = 'test'
  }
  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/your-repo'
      }
    }
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
    stage('Test') {
      steps {
        sh 'npm test'
      }
    }
  }
  post {
    success {
      echo 'Build succeeded!'
    }
    failure {
      echo 'Build failed!'
    }
  }
}

2. Stages and Steps
    Stages: Logical breakdown of the CI process (e.g., Build, Test, Deploy)
    Steps: The actual shell/script/command run in each stage

3. Environment Variables in Jenkinsfile
    Use the environment block to set variables used across the pipeline

4. Post Actions
    The post block handles notifications and cleanup tasks after job execution — regardless of success or failure

