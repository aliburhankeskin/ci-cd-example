pipeline {
  
  agent none
  
  stages {
  	 stage('Clone Repository') {
         checkout scm
    }
    stage('Docker Build') {
        sh "docker build -t node-api ."
    }

    stage('App Start') {
        sh "docker run -dp 3000:3000 node-api"
    }
  }
}