✅ Day 4 Notes – Advanced Pipeline Concepts
🗓️ Day 4 – Advanced Pipeline Concepts
🎯 Goal: Learn shared libraries, scripted pipelines, and reusable logic

🧠 Learn (Theory):
- Scripted Pipelines vs Declarative Pipelines
    Scripted: More flexible, Groovy-based, great for complex logic
    Declarative: More readable, structured, ideal for common CI/CD pipelines

- Parallel Steps
    Run multiple stages simultaneously (e.g., unit tests, integration tests, linting)

- Input Steps
    Allow manual approvals (e.g., before deployment)

- Shared Libraries
    Custom reusable pipeline functions for DRY (Don't Repeat Yourself) workflows

🛠️ Hands-on:
    - Implemented a scripted pipeline using node { ... } blocks with if conditions
    - Used parallel steps to simulate test stages (unit, integration, lint)
    - Added an input step to pause the pipeline for manual approval
    - Created a basic shared library and called a custom function inside the pipeline

✅ Checkpoint Achieved:
    - Can now confidently write both scripted and declarative pipelines
    - Built a Jenkins job that runs parallel steps with conditional logic and approval checkpoints
    - Explored how shared libraries help modularize and clean up Jenkins pipelines

🔍 What I Learned Today:
1. cripted Pipelines

    node {
    stage('Clone') {
        git 'https://github.com/your-repo'
    }
    stage('Build') {
        if (env.BRANCH_NAME == 'main') {
        sh 'npm run build'
        }
    }
    }
2. Parallel Steps

    parallel (
    "Unit Tests": { sh 'npm run test:unit' },
    "Integration Tests": { sh 'npm run test:integration' },
    "Lint": { sh 'npm run lint' }
    )

3. Input Steps

    input message: 'Approve to Deploy?', ok: 'Deploy'

4. Shared Libraries

    - Structure:
        vars/
        sayHello.groovy
        
    - Usage:
        sayHello("World")

    - Function:
        def call(name) {
        echo "Hello, ${name}!"
        }