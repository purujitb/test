pipeline {

  agent { label 'single_cpu_worker||multi_cpu_worker' }
  
  stages {
    stage('Build') {
      steps {
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
