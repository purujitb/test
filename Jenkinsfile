pipeline {

  agent { label 'single_cpu_worker||multi_cpu_worker' }
  
  stages {
  
  stage('GetNodeName') {
    steps{
    def node_name = "${NODE_NAME}"
    echo "The Node Name is: ${node_name}"
    }
    }
  
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
