node  {

    try {

   stage('Clone repository') {
            checkout scm
        }
    stage('Build image') {
            sh "docker build -t node-api ."
    }

    stage('Restart Application') {
            sh "docker run -dp 3000:3000 node-api"
            echo = "Compose Upppp!"
    }

    } catch (e) {
       currentBuild.result = "FAILED"
       throw e
     } finally {
    }

}
