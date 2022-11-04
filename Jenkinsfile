node  {

    try {

        stage('Clone repository') {
            checkout scm
        }
        
        // stage('Remove Old Image') {
        //     sh "docker rmi -f node-api"
        // }

        stage('Build image') {
            sh "docker build -t node-api ."
        }

        // stage('App Start') {
        //     sh "docker run -dp 3000:3000 node-api"
        // }

        stage('Restart Application') {
            sh "docker-compose down"
            sh "docker-compose up -d"
            echo = "Compose Upppp!"
            sh "docker image prune -a"
        }

    } catch (e) {
       currentBuild.result = "FAILED"
       throw e
     } finally {
    }

}