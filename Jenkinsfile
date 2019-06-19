pipeline {

  agent any
  
  stages {
  
    stage('Build') {
      steps {
       echo "NODE_NAME = ${env.NODE_NAME}"
        echo "Building"
      }
    }

    stage('Test') {
      steps {
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
