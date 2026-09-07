pipeline{
    // This is Pre-build section
    agent{
        node {
            label 'Agent-1'
        }
    }
    
    environment{
        Learn = "Jenkins"
    }

    options{
        timeout(time: 10, unit: 'MINUTES')
        disableConcurrentBuilds()
    }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    // This is build section
    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                    echo 'Building'
                    echo '$Learn'
                    #env
                    #sleep 11
                    echo "GitHub Webhook testing automatic"
                    echo "Hello ${params.PERSON}"
                    echo "Biography: ${params.BIOGRAPHY}"
                    echo "Toggle: ${params.DEPLOY}"
                    echo "Choice: ${params.CHOICE}"
                    echo "Password: ${params.PASSWORD}"
                    """
                }
            }
        }
    
    // This is test section
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
    // This is Deploy section
        stage('Deploy'){
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }


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
