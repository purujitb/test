pipeline {
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
        docker.build("generalx/hw_test")
      }
    }
  }
}
