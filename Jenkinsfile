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
         stage ('Docker Build'){
            steps {
                script {
                    docker.build("nethrashreec/myapp:${TAG}")
                }
            }
        }
       
        
    }
}
