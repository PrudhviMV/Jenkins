pipeline{
    agent{
        node {
            label 'Agent-1'
        }
    }
    
    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                    echo 'Building'
                    """
                }
            }
        }
    

        stage('Test'){
            steps{
                script{
                    sh """"
                    echo 'Testing'
                    """
                }
            }
        }

        stage('Deploy'){
            steps{
                script{
                    sh """
                    echo 'Deploying'
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
