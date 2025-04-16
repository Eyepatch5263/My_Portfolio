@Library("Shared") _

pipeline {
    agent {
        label "jenkins-slave"
    }
    stages {
        stage("Start") {
            steps {
                script {
                    hello()
                }
            }
        }
        stage("Cloning Code") {
            steps {
                script {
                    clone("https://github.com/Eyepatch5263/My_Portfolio.git", "main")
                }
            }
        }
        stage("Build Docker Image") {
            steps {
                script {
                    docker_build("portfolio", "latest", "eyepatch5263")
                }
            }
        }
        stage("Push to Docker Hub") {
            steps {
                script {
                    docker_push("portfolio", "latest", "eyepatch5263")
                }
            }
        }
        stage("Starting Docker Container") {
            steps {
                script {
                    docker_compose()
                }
            }
        }
    }
}
