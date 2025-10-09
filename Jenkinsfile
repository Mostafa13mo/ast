pipeline {
    agent any
    tools{
        nodeJs 'nodeJs 24.10.0'
    }
    stages {
        stage('Hello') {
            steps {
                echo 'DEBUG: this is the updated Jenkinsfile'
                echo '✅ Jenkinsfile is being executed successfully!'
                sh 'echo "Running shell command..."'
            }
        }
        stage('Hello2') {
            steps {
              sh 'npm -v'
            }
        }
    }
}
