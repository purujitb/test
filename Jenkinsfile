pipeline {

  agent any
  
  stages {
    stage('Sonarqube') {
      environment {
        scannerHome = tool 'SonarScannerFE'
      }
      steps {
        withSonarQubeEnv('SonarFE') {
          sh "${scannerHome}/bin/sonar-scanner"
        }
        timeout(time: 10, unit: 'MINUTES') {
          waitForQualityGate abortPipeline: true
        }
      }
    }
    
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
