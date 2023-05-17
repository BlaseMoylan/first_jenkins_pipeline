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
        script{
        def dockertool = tool name: 'docker-latest-tool', type: 'org.jenkinsci.plugins.docker.commons.tools.DockerTool'
          env.PATH = "${dockerTool}/bin:${env.PATH}"
        }
        withCredentials([usernamePassword(credentialsId: 'personal-docker-credentials',usernameVariable: 'DOCKER_USERNAME',passwordVariable:'DOCKER_PASSWORD')]){
          sh "echo ${DOCKER_USERNAME}"
        }
        sh "docker --version"
      }
        
    }
    
  }
}
