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
        app = docker.build("generalx/hw_test")
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
      }
    }
  }
}
