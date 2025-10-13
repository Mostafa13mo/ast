pipeline {
    agent any
    
  //  environment {
  //      DOCKER_BUILDKIT = '1'
   // }
    
    // tools {
    //     nodejs 'node 24.10.0'
    // }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Mostafa13mo/ast.git'
            }
        }
        stage('Debug - List Files') {
            steps {
                sh '''
                    echo "=== Current directory ==="
                    pwd
                    echo "=== All files ==="
                    ls -la
                    echo "=== Git status ==="
                    git status
                    echo "=== Git log ==="
                    git log -1 --oneline
                '''
            }
        }
        
        stage('Verify Dockerfile') {
            steps {
                sh """
                    echo "=== Dockerfile content ==="
                    cat Dockerfile
                    echo "=== Dockerfile details ==="
                    ls -la Dockerfile
                    stat Dockerfile
                """
            }
        }
        
        stage('Hello') {
            steps {
                echo 'DEBUG: this is the updated Jenkinsfile'
                echo '✅ Jenkinsfile is being executed successfully!'
                sh 'echo "Running shell command..."'
            }
        }
        
        // stage('npm build stage') {
        //     steps {
        //         sh 'npm -v'
        //     }
        // }
        
        // stage('docker build') {
        //     steps {
        //         sh 'docker build -t docker.io/mostafa137/web-image2 .'
        //     }
        // }
        
        // stage('docker push') {
        //     steps {
        //         withCredentials([usernamePassword(credentialsId: 'mycrid', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
        //             sh """
        //                 echo "$PASSWORD" | docker login -u "$USERNAME" --password-stdin
        //                 docker push docker.io/mostafa137/web-image2
        //             """
        //         }
        //     }
        }   
        stage('deploy') {
            steps {
               sshagent(credentials: ['credent']) {
                     sh 'ssh -o StrictHostKeyChecking=no -p 2222 ubuntu@127.0.0.1 "uptime"'

                 
                }
            }
        }    
    }
}
