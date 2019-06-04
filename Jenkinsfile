pipeline {
  environment {
    registry = "generalx/hello_docker"
    registryCredential = 'docker-hub-credentials'
  }

  agent any
  
  stages {
    stage('Build') {
      steps {
        echo 'building'
      }
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
