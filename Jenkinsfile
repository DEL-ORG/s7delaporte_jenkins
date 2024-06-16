pipeline {
    agent any

options {
  buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '3', numToKeepStr: '3')
  disableConcurrentBuilds()
}
    environment {
        APP_NAME = 'my-application'
        DEPLOY_ENV = 'production'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Starting the Build stage...'
                // Replace with your actual build commands
                sh 'echo "Compiling the application..."'
                // Example: sh './gradlew build'
            }
        }

        stage('Test1234') {
            steps {
                echo 'Starting the Test stage...'
                // Replace with your actual test commands
                sh 'echo "Running tests..."'
                // Example: sh './gradlew test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Starting the Deploy stage...'
                // Replace with your actual deploy commands
                sh """
                if [ "${DEPLOY_ENV}" == "production" ]; then
                    echo 'Deploying to production environment'
                    # Add production deployment commands here
                else
                    echo 'Deploying to staging environment'
                    # Add staging deployment commands here
                fi
                """
                // Example: sh './gradlew deploy'
            }
        }

        stage('Cleanup') {
            steps {
                echo 'Starting the Cleanup stage...'
                // Replace with your actual cleanup commands
                sh 'echo "Cleaning up the environment..."'
                // Example: sh 'rm -rf build'
            }
        }

        stage('Confirmation') {
            steps {
                echo 'Send confirmation message'
                // Replace with your actual cleanup commands
                sh '''ls
                pwd
                ls -l'''
            }
        }git 
    }

    post {
        always {
            echo 'This will always run after every stage, success or failure.'
            // Add any final cleanup or notifications here
            sh 'echo "Pipeline finished"'
        }
        success {
            echo 'This will run only if the pipeline succeeds.'
            // Add success notifications here, e.g., Slack, email, etc.
        }
        failure {
            echo 'This will run only if the pipeline fails.'
            // Add failure notifications here, e.g., Slack, email, etc.
        }
    }
}
