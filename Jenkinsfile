currentBuild.displayName = "mydockerwebapp-#"+currentBuild.number
pipeline{
    agent any
    //environment {
    //DOCKERHUB_CREDENTIALS = credentials('docker-hub-auth')
  //}
    stages{
        stage("Git checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/kvaravinda/example-voting-app'
            }
        }
        stage("docker build"){
            steps{
                sh "docker build ./vote/ -t kvaravinda/mydockerapp:vikas"
                //sh 'echo $DOCKERHUB_CREDENTIALS_PSW |docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                withCredentials([string(credentialsId: 'dockerhubpwd', variable: 'dockerhubpasswd')]) {
                sh "docker login -u kvarvinda -p ${dockerhubpasswd}"
                }
                sh "docker push kvaravinda/mydockerapp:vikas"
            }
        }
    }
}
