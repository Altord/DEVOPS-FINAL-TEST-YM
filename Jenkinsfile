pipeline {
    agent any

    environment {
        NODE_VERSION = '18.16.1'
    }

    triggers {
        pollSCM('H/5 * * * *') 
    }

    tools {
        nodejs 'nodejs' 
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                bat 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                bat 'npm run build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat(
                    script: 'npm test',
                    // Continue even if there's an error (e.g., no tests found)
                    returnStatus: true
                )
            }
            post {
                always {
                    echo 'Publishing test results...'
                    // If you had test results to publish, the command would go here.
                    // You can use the returnStatus to decide whether to publish or not.
                }
            }
        }

        stage('Static Analysis') {
            steps {
                echo 'Analyzing code...'
                // Placeholder for static analysis tools.
                // Use returnStatus: true if you have a tool that may not always produce output.
                bat(
                    script: 'echo "Static analysis step"',
                    returnStatus: true
                )
            }
        }

        stage('Deliver') {
            steps {
                echo 'Delivering the artifact...'
                // Placeholder for delivery command.
                bat(
                    script: 'echo "Deliver artifact step"',
                    returnStatus: true
                )
            }
        }

        stage('Deploy to Dev') {
            steps {
                echo 'Deploy to Dev environment step executed here'
                // Placeholder for deploy command.
                bat(
                    script: 'echo "Deploy to Dev step"',
                    returnStatus: true
                )
            }
        }

        stage('Deploy to QAT') {
            steps {
                echo 'Deploy to QAT environment step executed here'
                // Placeholder for deploy command.
                bat(
                    script: 'echo "Deploy to QAT step"',
                    returnStatus: true
                )
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploy to Staging environment step executed here'
                // Placeholder for deploy command.
                bat(
                    script: 'echo "Deploy to Staging step"',
                    returnStatus: true
                )
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploy to Production environment step executed here'
                // Placeholder for deploy command.
                bat(
                    script: 'echo "Deploy to Production step"',
                    returnStatus: true
                )
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
        always {
            echo 'This will always run at the end of the pipeline.'
            //Testing 2
        }
    }
}
