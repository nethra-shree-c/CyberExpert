pipeline {
    agent any

    environment {
        DATE = new Date().format('yy.M')
        TAG = "${DATE}.${BUILD_NUMBER}"
    }

    stages {
        stage ('Build') {
            steps {
                echo "Command to check out code from github to come here"
                echo "${TAG}"
            }
        }
         stage('Build and Push Image') {
      steps {
        script {
          def dockerImage = docker.build("mydockerhubaccount/myapp:${env.BUILD_ID}")
            sh 'docker build -t mydockerhubaccount/myapp:9 .'
          docker.withRegistry('https://hub.docker.com/', 'dockerhubid') {
            dockerImage.push()
          }
        }
      }
    }
       
        
    }
}