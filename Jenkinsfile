pipeline {
    agent any
    tools{
        nodejs 'node 24.10.0'
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
                  docker build -t docker.io/mostafa137/web-image
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
