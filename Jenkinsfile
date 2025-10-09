pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                echo 'Pipeline is working!'
                sh 'echo "npm version:" && npm -v'
            }
        }
    }
}

