pipeline {
    agent any
    tools {nodejs "NODEJS"}
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test'){
          steps{
            sh 'npm run lint'
          }
        }
        stage('Deliver') {
            steps {
                sh 'npm run build'
                sh 'cp -a dist/immoclient/. /var/www/angular'
            }
        }
    }
}
