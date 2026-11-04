pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps { checkout scm }
        }
        stage('Build') {
            steps { echo "Building branch ${env.BRANCH_NAME}" }
        }
        stage('Deploy') {
            when { branch 'main' }
            steps { echo 'Deploying from main...' }
        }
        stage('Lint / Extra Checks') {
            when { branch pattern: "feature/.*", comparator: "REGEXP" }
            steps { echo 'Running extra checks on feature branch...' }
        }
    }
}

