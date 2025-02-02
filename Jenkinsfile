#!/usr/bin/env groovy

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
                    def dockerCmd = 'docker run -p 3080:3080 -d iwaseemdevops/my-app:11201-12'
                    sshagent(['ec2-server-key']) {
                       sh "ssh -o StrickHostKeyChecking=no ec2_user@43.204.111.197 ${dockerCmd}" 
                    }
                }
            }
        }
    }
}
