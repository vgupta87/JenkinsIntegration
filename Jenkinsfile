pipeline {
    agent any

    triggers {
        githubPush() // This sets up a webhook trigger for GitHub push events
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                // Add your build steps here, e.g., compiling code
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add your test steps here, e.g., unit tests
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the project...'
                // Add your deployment steps here, e.g., deploying to a server
            }
        }
    }

    post {
        success {
            echo 'Build was successful!'
            // Optionally, you can add notifications or other actions here
        }
        failure {
            echo 'Build failed!'
            // Optionally, you can add notifications or other actions here
        }
    }
}
