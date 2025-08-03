pipeline {
    agent none
    stages {
        stage('Test Hello World in Multiple OS') {
            parallel {
                stage('Python') {
                    agent {
                        docker {
                            image 'python:3.12-slim'
                        }
                    }
                    steps {
                        sh 'python hello.py'
                    }
                }
                stage('C (gcc)') {
                    agent {
                        docker {
                            image 'gcc:latest'
                        }
                    }
                    steps {
                        sh 'gcc hello.c -o hello_c && ./hello_c'
                    }
                }
                stage('Java') {
                    agent {
                        docker {
                            image 'openjdk:21-slim'
                        }
                    }
                    steps {
                        sh 'javac HelloWorld.java && java HelloWorld'
                    }
                }
                stage('Node.js') {
                    agent {
                        docker {
                            image 'node:20-slim'
                        }
                    }
                    steps {
                        sh 'node hello.js'
                    }
                }
            }
        }
    }
}
