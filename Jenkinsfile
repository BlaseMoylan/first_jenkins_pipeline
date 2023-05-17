pipeline {
  agent any
  
  stages{
    
    stage('build'){
      steps{
        sh 'echo "building the aplication..."'
      }
    }
    stage('Docker'){
      steps{
        withCredentials([usernamePassword(credentialsId: 'personal-docker-credentials',usernameVariable: 'DOCKER_USERNAME',passwordVariable:'DOCKER_PASSWORD')]){
          sh "echo ${DOCKER_USERNAME}"
        }
        sh "docker --version"
      }
        
    }
    
  }
}
