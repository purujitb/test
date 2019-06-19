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
      label 'multi_cpu_worker'
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
