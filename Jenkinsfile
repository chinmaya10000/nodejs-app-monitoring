pipeline {
    agent any

    stages {
        stage('s1-any-agent') {
            steps {
                script {
                    sh 'cat /etc/os-release'
                    sh 'node -v'
                    sh 'npm -v'
                }
            }
        }
        stage('s1-my-agent') {
            agent {
                label 'slave-1'
            }
            steps {
                script {
                    sh 'cat /etc/os-release'
                    sh 'node -v'
                    sh 'npm -v'
                }
            }
        }
        stage('s3-Docker Image Agent') {
            agent {
                node {
                    label 'slave-1'
                }
            }
             steps {
                script {
                    docker.image('node:18-alpine').inside {
                        sh 'cat /etc/os-release'
                        sh 'node -v'
                        sh 'npm -v'
                    }
                }
             }
        }
    }
}
