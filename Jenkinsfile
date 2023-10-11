currentBuild.displayName = "mydockerwebapp-#"+currentBuild.number
pipeline{
    agent any
    stages{
        stage("Git checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/kvaravinda/example-voting-app'
            }
        }
        stage("docker build"){
            steps{
                sh "sudo docker build ./vote/ -t kvaravinda/mydockerapp:v1"
            }
        }
    }
}
