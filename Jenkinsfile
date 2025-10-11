pipeline {
    agent any
    tools{
        nodejs 'nodeJs 24.10.0'
    }
    stages {
        stage('Hello') {
            steps {
                echo 'DEBUG: this is the updated Jenkinsfile'
                echo '✅ Jenkinsfile is being executed successfully!'
                sh 'echo "Running shell command..."'
            }
        }
        stage('npm build stage') {
            steps {
              sh 'npm -v'
            }
        }
        stage('docker build') {
            steps {
              sh """
                  docker build docker.io/mostafa137/
              """
            }
        }
        stage('docker push') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'mycrid', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) 
              sh """
                 docker login -u $USERNAME -p $PASSWORD
              """
            }
        }    
    }
}
