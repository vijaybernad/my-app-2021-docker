pipeline{
  agent any
  tool name: 'maven', type: 'maven'

  stages{
    stage('Maven Build'){
      steps{       
        sh "mvn clean package"
      }
    }

    stage('Docker Build Image'){
      steps{
       sh "docker build . -t vbarnad/2021myapp:v1"
      }
    }
    
    stage('push to docker hub'){
      steps{
       echo "deploy"
        
      }
    }

    stage('dev-deploy'){
      steps{
         echo "deploy"
      }
    }
  }
}

