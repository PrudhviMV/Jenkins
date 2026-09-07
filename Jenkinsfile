pipeline{
    agent{
        node {
            label 'Agent-1'
        }
    }
    
    environment{
        Learn = Jenkins
    }

    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                    echo 'Building'
                    echo '$Learn'
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

        success{
            echo 'I will run if it is success'
        }

        failure{
            echo 'I will run if it is failure'
        }
    }
}
