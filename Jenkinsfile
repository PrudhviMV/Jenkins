pipeline{
    agent{
        node {
            label 'Agent-1'
        }
    }
    
    environment{
        Learn = "Jenkins"
    }

    options{
        timeout(time: 10, Unit: 'SECONDS')
    }

    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                    echo 'Building'
                    echo '$Learn'
                    env
                    """
                }
            }
        }
    

        stage('Test'){
            steps{
                script{
                    sh """
                    echo 'Testing'
                    echo '$Learn'
                    """
                }
            }
        }

        stage('Deploy'){
            steps{
                script{
                    sh """
                    echo 'Deploying'
                    echo '$Learn'
                    """
                }
            }
        }
    }

    post{
        always{
            echo 'I will run always'
            cleanWs()
        }

        aborted{
            echo "Pipeline is aborted for "
        }
        success{
            echo 'I will run if it is success'
        }

        failure{
            echo 'I will run if it is failure $BUILD_URL and $BUILD_TAG'
        }
    }
}
