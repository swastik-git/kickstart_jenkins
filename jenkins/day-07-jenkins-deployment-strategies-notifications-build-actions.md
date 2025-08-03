✅ Day 7 – Jenkins & DevOps Learning Notes
🔁 Deployment Strategies
Understanding different deployment strategies helps reduce downtime and risk during updates:

1. Blue-Green Deployment
    -Two identical environments: one active (live), one idle (staging).
    -New version is deployed to idle environment.
    -Traffic is switched after verification.
    -Pros: zero-downtime, easy rollback.
    -Cons: doubles infrastructure cost.

2. Rolling Deployment
    -Gradually replaces old version with new one instance-by-instance.
    -Avoids downtime, can observe errors early.
    -Rollback is slower compared to Blue-Green.

3. Canary Deployment
    -Releases new version to small subset of users.
    -Monitors for issues before full rollout.
    -Safer for high-risk features.

📣 Build Notifications in Jenkins
✅ Why Use Them?
    -Get real-time updates about build status.
    -Notify teams or Slack channels when builds fail, succeed, or are unstable.

🔧 Tools & Methods:
    -Slack Notification Plugin – customizable message formats.
    -Email Extension Plugin – detailed email reports with logs.
    -Notifications can be added as post-build actions.

    post {
    success {
        slackSend channel: '#ci-cd', message: '✅ Build Passed!'
    }
    failure {
        emailext body: '❌ Build Failed', to: 'devops@team.com'
    }
    }

🔄 Pre-Build & Post-Build Actions
Pre-Build:
    -Set environment variables.
    -Clean workspace.
    -Pull secrets or artifacts.
    -Run setup/test validation scripts.

Post-Build:
    -Archive artifacts (JAR, WAR, ZIP).
    -Trigger another job or pipeline.
    -Send notifications.
    -Run cleanup tasks.

💡 Takeaways
    -Deployment isn’t just about shipping code — it’s about doing it safely and predictably.

    -Proper notifications reduce debugging time.

    -Pre/post build actions give you control and flexibility for production-grade CI/CD pipelines.