pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                echo '✅ Jenkinsfile is being executed successfully!'
                sh 'echo "Running shell command..."'
            }
        }
        stage('List files') {
            steps {
                sh 'pwd && ls -la'
            }
        }
    }
}
