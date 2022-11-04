node  {

    try {

        stage('Clone repository') {
            checkout scm
        }
        
        stage('Remove Old Image') {
            sh "docker rmi -f node-api"
        }

        stage('Build image') {
            sh "docker build -t node-api ."
        }

        stage('App Start') {
            sh "docker run -dp 3000:3000 node-api"
        }

    } catch (e) {
       currentBuild.result = "FAILED"
       throw e
     } finally {
    }

}