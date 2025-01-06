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
            sh 'npm lint'
            sh 'npm run test --watch=false'
          }
        }
        stage('Deliver') {
            steps {
                sh 'ng build --configuration production'
                sh 'cp -a dist/immoclient/. /var/www/angular'
            }
        }
    }
}
