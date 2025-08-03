pipeline {
    agent none
    stages {
        stage('Test Hello World in Multiple OS') {
            parallel {
                stage('Ubuntu 22.04') {
                    agent {
                        docker {
                            image 'ubuntu:22.04'
                            args '-u root'
                        }
                    }
                    steps {
                        sh 'apt-get update && apt-get install -y python3'
                        sh 'python3 hello.py'
                    }
                }
                stage('Ubuntu 24.04') {
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
                stage('Alpine 3.18') {
                    agent {
                        docker {
                            image 'alpine:3.18'
                            args '-u root'
                        }
                    }
                    steps {
                        sh 'apk add --no-cache python3'
                        sh 'python3 hello.py'
                    }
                }
                stage('Alpine 3.19') {
                    agent {
                        docker {
                            image 'alpine:3.19'
                            args '-u root'
                        }
                    }
                    steps {
                        sh 'apk add --no-cache python3'
                        sh 'python3 hello.py'
                    }
                }
                stage('Debian 12') {
                    agent {
                        docker {
                            image 'debian:12'
                            args '-u root'
                        }
                    }
                    steps {
                        sh 'apt-get update && apt-get install -y python3'
                        sh 'python3 hello.py'
                    }
                }
                stage('Debian latest') {
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
                stage('Fedora 39') {
                    agent {
                        docker {
                            image 'fedora:39'
                            args '-u root'
                        }
                    }
                    steps {
                        sh 'dnf install -y python3'
                        sh 'python3 hello.py'
                    }
                }
                stage('Fedora latest') {
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
