pipeline {
    agent any
    tools {
        go 'go-1.11.4'
    }
    environment {
        GO111MODULE = 'on'
    }
    stages {
        stage("build") {
            steps {
                echo 'BUILD EXECUTION STARTED'
                sh 'go version'
                sh 'docker build . -t anjardanis/simple-go'
            }
        }
        stage("deploy") {
            steps {
                echo 'Deploy STARTED'
                sh 'go version'
                sh 'git clone https://github.com/anjardanis/simple-go.git'
                sh 'cd simple-go && nohup go run server.go &'
            }
        }
    }
}