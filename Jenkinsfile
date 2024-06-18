pipeline {
    agent any //all agents
    tools {
        go 'go-1.22.4' //Installed latest version 
    }
    environment {
        GO111MODULE = 'on' //Env variable required to be set to on
    }
    stages {
        stage('Build') {
            steps {
                sh 'go mod init' //go: cannot find main module, but found .git/config in /home/armando/.jenkins/workspace/Java-projects/go-pipeline
                sh 'go build' //Running go command defined previously
            }
        }
    }
}