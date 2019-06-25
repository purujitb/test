pipeline {

  agent any
  
  stages {
  
    stage('Build') {
      steps {
       echo "NODE_NAME = ${env.NODE_NAME}"
        echo "Building"
      }
    }

    stage('Test on worker 1') {
    agent {
      label 'worker3'
    }
      steps {
      echo "NODE_NAME = ${env.NODE_NAME}"
        echo 'Testing'
      }
    }

    stage('Deploy Image') {
      steps{
        echo 'Deploying'
      }
    }
    

  }
}
