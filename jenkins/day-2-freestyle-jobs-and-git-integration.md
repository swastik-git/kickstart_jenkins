🗓️ Day 2 – Freestyle Jobs & Git Integration
🎯 Goal: Automate builds by integrating Jenkins with a GitHub repository.

🧠 Learn (Theory):
-Difference between Freestyle Jobs and Pipeline Jobs
-Source Code Management in Jenkins (Git integration)
-Build Triggers: Poll SCM vs Webhooks
-Role of GitHub in enabling automated CI workflows

🛠️ Hands-on:
-Created a Freestyle Job connected to a GitHub repo
-Configured Build Triggers using:

    SCM Polling (H/5 * * * *)
    Webhook (GitHub → Jenkins)

-Added build step: npm install && npm test
-Observed automated job executions on each Git push ✅

✅ Checkpoint Achieved:
Jenkins now auto-builds on code push to GitHub
Shell steps integrated in build process
SCM connection and webhook tested successfully

🔍 What I Learned Today:

1. Freestyle Jobs vs Pipelines in Jenkins

    -Freestyle: Simpler, UI-based, good for small tasks
    -Pipeline: Code-defined, scalable, better for complex workflows
    👉 Freestyle is a good starting point to understand job configuration.

2. ource Code Management in Jenkins
    -Direct integration with GitHub and Git-based repos
    -Can pull code automatically for every build
    -Configuration: Add repo URL + credentials (if private)

3. Build Triggers – Poll SCM vs Webhooks

    -Poll SCM: Jenkins checks Git at regular intervals
    -Example: H/5 * * * * → every 5 minutes

    - Webhook: GitHub notifies Jenkins immediately on code push
    👉 Webhook is more efficient and real-time.

4. Writing Build Steps for Node.js Projects
    -In the “Build” section of Freestyle Job, added a shell step:

    npm install
    npm test
✔️ This ensures dependencies are installed and tests run on every push.

5. Webhook Configuration (GitHub → Jenkins)

    -In GitHub repo → Settings → Webhooks → Add Jenkins URL
    -Jenkins → Job → Configure → Enable “GitHub hook trigger for GITScm polling”
    -Validate connection and test push event