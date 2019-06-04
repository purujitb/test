pipeline {
  environment {
    registry = "generalx/hello_docker"
    registryCredential = 'docker-hub-credentials'
  }

  agent any
  
  stages {
    
    stage('Checkout') {
      git url: https://github.com/fastestimator/test.git", branch: master
    }
  
    stage('Build') {
        echo "Building"
    }

    stage('Docker deploy') {
      steps {
        echo 'Deploying to docker'
        script {
            docker.build registry
        }
      }
    }

    stage('Deploy Image') {
      steps{
        script {
          docker.withRegistry( '', registryCredential ) {
            dockerImage.push()
          }
        }
      }
    }

    stage('Remove Unused docker image') {
      steps{
        sh "docker rmi $registry"
      }
    }

  }
}
