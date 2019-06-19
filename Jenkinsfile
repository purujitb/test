pipeline {
  environment {
    registry = "generalx/hello_docker"
    registryCredential = 'docker-hub-credentials'
    dockerImage = ''
  }

  agent { label 'single_cpu_worker||multi_cpu_worker' }
  
  stages {
    stage('Build') {
      steps {
        echo "Building"
      }
    }

    stage('Docker deploy') {
      steps {
        echo 'Deploying to docker'
        script {
            dockerImage = docker.build registry
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
