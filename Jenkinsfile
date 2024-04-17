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
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'npm run build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm test'
            }
            post {
                always {
                    echo 'Publishing code coverage results...'
                   
                }
            }
        }

        stage('Static Analysis') {
            steps {
                echo 'Analyzing code...'
                
            }
        }

        stage('Deliver') {
            steps {
                echo 'Delivering the artifact...'
              
            }
        }

        stage('Deploy to Dev') {
            steps {
                echo 'Deploy to Dev environment step executed here'
            }
        }

        stage('Deploy to QAT') {
            steps {
                echo 'Deploy to QAT environment step executed here'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Deploy to Staging environment step executed here'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deploy to Production environment step executed here'
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
        }
    }
}
