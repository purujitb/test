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
        script {
            docker.build("generalx/hw_test")
        }
      }
    }
  }
}
