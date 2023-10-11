currentBuild.displayName = "mydockerwebapp-#"+currentBuild.number
pipeline{
    agent any
    stages{
        stage("Git checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/kvaravinda/example-voting-app'
            }
        }
    }
}
