pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/vyshnavibhimavarapu/saleor.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t vyshnavibhimavarapu/saleor-core:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push vyshnavibhimavarapu/saleor-core:DEV'
            }
        }
    }
}