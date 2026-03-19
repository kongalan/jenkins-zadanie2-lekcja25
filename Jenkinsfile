pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/kongalan/jenkins-zadanie2-lekcja25.git'
            }
        }

        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Report') {
            steps {
                sh 'npm test > report.txt'
                archiveArtifacts artifacts: 'report.txt', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Build zakończony sukcesem'
        }
        failure {
            echo 'Build NIE powiódł się'
        }
    }
}
