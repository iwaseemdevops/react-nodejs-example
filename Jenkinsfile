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
                    sshagent(['ec2-server-key-2']) {
                        // First, check if SSH connection works
                        sh "ssh -o StrictHostKeyChecking=no ec2_user@43.204.111.197 'echo SSH is working'"

                        // Check if docker run command is passed correctly
                        sh "echo docker run -p 3080:80 -d iwaseemdevops/my-app:11201-12"

                        // Finally, run the docker command with SSH
                        sh "ssh -o StrictHostKeyChecking=no ec2_user@43.204.111.197 \"docker run -p 3080:80 -d iwaseemdevops/my-app:11201-12\""
                    }
                }
            }
        }
    }
}
