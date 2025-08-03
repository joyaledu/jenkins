pipeline {
    agent none
    stages {
        stage('Test Hello World in Multiple OS') {
            parallel {
                stage('Python') {
                    agent { docker { image 'python:3.12-slim' } }
                    steps { sh 'python hello.py' }
                }
                stage('C (gcc)') {
                    agent { docker { image 'gcc:latest' } }
                    steps { sh 'gcc hello.c -o hello_c && ./hello_c' }
                }
                stage('Java') {
                    agent { docker { image 'openjdk:21-slim' } }
                    steps { sh 'javac HelloWorld.java && java HelloWorld' }
                }
                stage('Node.js') {
                    agent { docker { image 'node:20-slim' } }
                    steps { sh 'node hello.js' }
                }
                stage('Go') {
                    agent { docker { image 'golang:1.22-alpine' } }
                    steps { sh 'go run hello.go' }
                }
                stage('Ruby') {
                    agent { docker { image 'ruby:3.3-alpine' } }
                    steps { sh 'ruby hello.rb' }
                }
                stage('Shell') {
                    agent { docker { image 'alpine:latest' } }
                    steps { sh 'sh hello.sh' }
                }
                stage('Fortran') {
                    agent { docker { image 'gcc:latest' } }
                    steps { sh 'gfortran hello.f90 -o hello_f && ./hello_f' }
                }
                stage('Haskell') {
                    agent { docker { image 'haskell:9.8.2' } }
                    steps { sh 'runghc hello.hs' }
                }
                stage('Rust') {
                    agent { docker { image 'rust:1.77' } }
                    steps { sh 'rustc hello.rs && ./hello' }
                }
                stage('C#') {
                    agent { docker { image 'mcr.microsoft.com/dotnet/sdk:8.0' } }
                    steps { sh 'dotnet new console -n HelloWorldApp && mv HelloWorld.cs HelloWorldApp/Program.cs && cd HelloWorldApp && dotnet run' }
                }
            }
        }
    }
}
