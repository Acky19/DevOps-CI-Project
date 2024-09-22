pipeline {
    agent any // Use any available agent

    tools{
         nodejs 'node16'
    }

    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    // Run npm install
                    sh 'npm install'
                }
            }
        }
        stage('Start Services') {
            steps {
                script {
                    // Run npm run compose:up
                    sh 'npm run compose:up'
                }
            }
        }
        stage('Run Integration Tests') {
            steps {
                script {
                    // Run npm run test:integration
                    sh 'npm run test:integration'
                }
            }
        }
        stage('Run End-to-End Tests') {
            steps {
                script {
                    // Run npm run test:e2e
                    sh 'npm run test:e2e'
                }
            }
        }
    }

    post {
        always {
            // Cleanup or other actions can be added here if needed
            echo 'Pipeline finished.'
        }
    }
}
