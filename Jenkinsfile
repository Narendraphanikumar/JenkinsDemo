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
                    docker.withRegistry('298635973747.dkr.ecr.us-east-1.amazonaws.com/sample-ecr') {
                        docker.image('jenkins/demo').push("$currentBuild.number")
                    }
                }
            }
        }
    }
}

                                        
