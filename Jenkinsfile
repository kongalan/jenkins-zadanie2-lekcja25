pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/TWOJ_LOGIN/jenkins-node-demo.git'
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
                echo 'Testy zakończone'
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
