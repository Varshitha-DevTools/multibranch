pipeline {
    agent any

    tools {
        maven 'Maven3'
    }

    stages {

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Production') {
            when {
                branch 'main'
            }
            steps {
                sh 'echo Deploying to PRODUCTION'
            }
        }

        stage('Deploy to Staging') {
            when {
                not { branch 'main' }
            }
            steps {
                sh 'echo Deploying to STAGING'
            }
        }
    }
}
