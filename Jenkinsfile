pipeline {
    agent any
    stages {
        stage('test') {
            steps {
                script {
                    echo "Testing the application..."
                }
            }
        }
        stage('build') {
            steps {
                script {
                    echo "Building the application..."
                }
            }
        }
        stage('deploy') {
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
