pipeline {
    // install golang 1.16 on Jenkins node
    agent any
    tools {
        go 'go1.14'
    }
    environment {
        GO114MODULE = 'on'
        CGO_ENABLED = 0 
        GOPATH = "${JENKINS_HOME}/jobs/${JOB_NAME}/builds/${BUILD_ID}"
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