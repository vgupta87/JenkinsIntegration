// Jenkinsfile for Generic Webhook Trigger
pipeline {
    agent any

    triggers {
        // Configure the Generic Webhook Trigger
        // Replace 'YOUR_TOKEN' with a secure token configured in your Jenkins job
        // The URL for the webhook would be: JENKINS_URL/generic-webhook-trigger/invoke?token=YOUR_TOKEN
        genericWebhook {
            token 'YOUR_TOKEN' // Token for authentication
            // Optional: Define variables to extract from the webhook payload
            // For example, if your webhook sends JSON with a 'message' field:
            // jsonPathFilter('$.message', 'MESSAGE_VAR')
            // This would make the 'MESSAGE_VAR' available in your pipeline.
        }
    }

    stages {
        stage('Checkout') {
            steps {
                // Replace with your SCM details
                git 'https://github.com/your-org/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                echo "Webhook triggered build!"
                // Access webhook payload variables if defined in triggers{}
                // echo "Message from webhook: ${MESSAGE_VAR}"
                sh 'mvn clean install' // Example build command
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test' // Example test command
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deployment logic here...'
            }
        }
    }
}
