node  {

    try {

        stage('Clone repository') {
            checkout scm
        }
        
        stage('Build image') {
            sh "docker build -t node-api . -v /var/run/docker.sock:/var/run/docker.sock"
        }

        stage('App Start') {
            sh "docker run -dp 3000:3000 node-api -v /var/run/docker.sock:/var/run/docker.sock"
        }

    } catch (e) {
       currentBuild.result = "FAILED"
       throw e
     } finally {
    }

}