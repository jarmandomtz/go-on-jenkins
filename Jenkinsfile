@Library('jenkins-standard-go-pipeline') _

standard()

/*pipeline {
    agent any //all agents
    tools {
        //go 'go-1.22.4' //Installed latest version 
        go 'go-1.12' //Installed latest version 
    }
    environment {
        GO111MODULE = 'on' //Env variable required to be set to on
    }
    stages {
        stage('Build') {
            steps {
                sh 'go build' //Running go command defined previously
            }
        }
        stage('Test') {
            steps {
                sh 'go test ./... -coverprofile=coverage.txt' //Running go command defined previously
                //sh 'curl -s https://codecov.io/bash | bash -s -'s
            }
        }
        stage('Code Analysis') {
            steps {
                sh 'curl -sfL https://install.goreleaser.com/github.com/golangci/golangci-lint.sh | bash -s -- -b $GOPATH/bin v1.18.0'
                sh 'golangci-lint run'
            }
        }
        stage('Release') {
            when {
                buildingTag()
            }
            environment {
                GITHUB_TOKEN = credentials('GITHUB_TOKEN')
            }
            steps {
                sh 'curl -sL https://git.io/goreleaser | bash'
            }
        }
    }
}/*