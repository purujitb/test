pipeline {

  agent { label 'single_cpu_worker||multi_cpu_worker' }
  
  stages {
  
    stage('Build') {
      steps {
       echo "NODE_NAME = ${env.NODE_NAME}"
        echo "Building"
      }
    }

    stage('Test') {
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
