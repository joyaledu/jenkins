pipeline {
    agent none
    stages {
        stage('Test Hello World in Multiple OS') {
            parallel {
                stage('Ubuntu 22.04') {
                    options {
                        stageLabel('Ubuntu 22.04 LTS')
                    }
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
                    options {
                        stageLabel('Ubuntu 24.04 LTS')
                    }
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
                    options {
                        stageLabel('Alpine Linux 3.18')
                    }
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
                    options {
                        stageLabel('Alpine Linux 3.19')
                    }
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
                    options {
                        stageLabel('Debian 12 Bookworm')
                    }
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
                    options {
                        stageLabel('Debian Latest')
                    }
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
                    options {
                        stageLabel('Fedora 39')
                    }
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
                    options {
                        stageLabel('Fedora Latest')
                    }
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
