pipeline {
    agent any

    stages {
        stage('Build Application') {
            steps {
                sh "npm install"
            }
        }
        stage('Run Unit Tests') {
            steps {
                sh "npm test"
            }
        }
        stage('Deploy Application') {
            steps {
            	sh "npm start &"
            }
        }
        stage('Run Functional Tests') {
            steps {
                sauce('538bc3bb-336f-4676-88d9-a20c582096ce') {
                  sh "npm run test-wdio"
                }
            }
        }
    }
}