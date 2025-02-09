pipeline {
    agent any  // This runs on any available agent

    stages {
        stage('Build') {
            steps {
                script {
                    // Your build steps (e.g., npm install for Node.js projects)
                    echo 'Building the project...'
                    
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Your test steps (e.g., running tests)
                    echo 'Running tests...'
                  
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Your deploy steps (e.g., pushing to production server)
                    echo 'Deploying the project...'
                    sshagent(['ec2-server-key']) {
                        
                    }
    
                }
            }
        }
    }

    post {
        always {
            // Steps that always run after the pipeline, e.g., cleanup
            echo 'Cleaning up...'
        }

        success {
            // Steps to take if the pipeline succeeds
            echo 'Pipeline succeeded!'
        }

        failure {
            // Steps to take if the pipeline fails
            echo 'Pipeline failed!'
        }
    }
}
