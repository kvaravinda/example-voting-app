currentBuild.displayName = "mydockerwebapp-#"+currentBuild.number
pipeline{
    agent any
    environment {
    DOCKERHUB_CREDENTIALS = credentials('docker-hub-auth')
  }
    stages{
        stage("Git checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/kvaravinda/example-voting-app'
            }
        }
        stage("docker build"){
            steps{
                sh "sudo docker build ./vote/ -t kvaravinda/mydockerapp:latest"
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW |sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                sh "sudo docker push kvaravinda/mydockerapp:latest"
            }
        }
    }
}
