pipeline {
  agent any
    
  tools {NodeJS "node"}
    
  stages {
        
    stage('Git') {
      steps {
        git 'https://github.com/aliburhankeskin/ci-cd-example.git'
      }
    }
     
    stage('Build') {
      steps {
        sh 'npm install'
        sh '<<Build Command>>'
      }
    }  
    
            
    stage('Test') {
      steps {
        sh 'node test'
      }
    }
  }
}