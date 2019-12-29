pipeline {
    agent any

    stages {

        stage('Docker build'){
            steps{
                script{
                    docker.build('jenkins/demo')
                }
            }
        }

        stage('Docker push'){
            steps{
                script{
                    docker.withRegistry('https://298635973747.dkr.ecr.us-east-1.amazonaws.com','ecr:us-east1:narendra/demo') {
                        docker.image('jenkins/demo').push("$currentBuild.number")
                    }
                }
            }
        }
    }
}

                                        
