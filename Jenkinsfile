pipeline{
  agent any
  tools {
        maven 'maven' 
    }
 

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
        withCredentials([usernamePassword(credentialsId: '70330e81-fb86-4f6d-bdd8-432f25d1b90d', passwordVariable: 'password', usernameVariable: 'name')]) {
          // some block
          sh "docker login -u ${name} -p ${password}"
          sh "docker push vbarnad/2021myapp:v1"
      }
        
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

