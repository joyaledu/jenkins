pipeline {
    agent none
    stages {
        stage('Test Hello World in Multiple OS') {
            parallel {
                stage('Ubuntu') {
                    agent {
                        docker {
                            image 'ubuntu:24.04'
                            args '-u root'
                        }
                    }
                    steps {
                        sh 'apt-get update && apt-get install -y python3'
                        sh 'python3 hello.py'
                    }
                }
                stage('Alpine') {
                    agent {
                        docker {
                            image 'alpine:latest'
                        }
                    }
                    steps {
                        sh 'apk add --no-cache python3'
                        sh 'python3 hello.py'
                    }
                }
                stage('Debian') {
                    agent {
                        docker {
                            image 'debian:latest'
                            args '-u root'
                        }
                    }
                    steps {
                        sh 'apt-get update && apt-get install -y python3'
                        sh 'python3 hello.py'
                    }
                }
                stage('Fedora') {
                    agent {
                        docker {
                            image 'fedora:latest'
                            args '-u root'
                        }
                    }
                    steps {
                        sh 'dnf install -y python3'
                        sh 'python3 hello.py'
                    }
                }
            }
        }
    }
}
