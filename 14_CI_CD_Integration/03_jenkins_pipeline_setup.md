# Jenkins Declarative Pipeline Setup

## What is Jenkins?
**Jenkins** is the most popular self-hosted open-source automation server used to configure custom CI/CD pipelines.

---

## Declarative Jenkinsfile Pipeline Pattern

Create a file named `Jenkinsfile` in the root of your project repository:

```groovy
// Jenkinsfile (Declarative Syntax)
pipeline {
    agent {
        // Run execution steps in a standardized Docker container
        docker { 
            image 'python:3.10-slim' 
        }
    }

    environment {
        BASE_URL = 'https://qa.ecommerce-demo.com'
        // Bind secrets securely from Jenkins Credentials Store
        DB_PASSWORD = credentials('qa-db-password')
    }

    stages {
        stage('Checkout') {
            steps {
                // Pull code from git
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Execute Tests') {
            steps {
                // Execute pytest regression marker
                sh 'pytest -m regression --junitxml=results.xml'
            }
        }
    }

    post {
        always {
            // Archive and display test results inside Jenkins UI
            junit 'results.xml'
        }
        success {
            echo "SUCCESS: All regression test cases passed successfully!"
        }
        failure {
            echo "FAILURE: Tests failed! Alerting Slack channels..."
            // Code block to send Slack notification
        }
    }
}
```

---

## 📌 Key Takeaways
- Jenkins Declarative pipelines are configured via a **`Jenkinsfile`** saved in source control.
- Use **Docker agents** to guarantee identical runtime environments.
- Use the **`post` block** to automatically publish test reports (`junit` format) and trigger slack alerts on failures.
