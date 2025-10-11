pipeline {
    agent any
    tools{
        nodejs 'node 24.10.0'
    }
    stages {
        stage('pwd stage') {
            steps {
              sh """
                    pwd
                    ls -la
                    find . -name "Dockerfile"
                """
            }
        }
        stage('Verify Dockerfile') {
            steps {
                sh  """
                    echo "=== Dockerfile content ==="
                    cat Dockerfile
                    echo "=== Dockerfile details ==="
                    file Dockerfile
                    stat Dockerfile
                """
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Mostafa13mo/ast.git'
            }
        }
        
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
                  cd /var/jenkins_home/workspace/test
                  docker build --no-cache -t docker.io/mostafa137/web-image2 .
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
