@Library('shared') _

pipeline {
    agent {label "agent-1"}

    stages {
        stage('cloning') {
            steps {
                clone("https://github.com/mohitDora/Jenkins-practice.git","main")
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    build("node-app","latest","mohitdora21")
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
                    push("dockerHubCred","node-app","latest")
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    compose()
                }
            }
        }
    }
}
