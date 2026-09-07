// pipeline {
//     agent any

//     stages {
//         stage('Build') {
//             steps {
//                 echo 'Building..'
//             }
//         }
//         stage('Test') {
//             steps {
//                 echo 'Testing..'
//             }
//         }
//         stage('Deploy') {
//             steps {
//                 echo 'Deploying....'
//             }
//         }
//     }
// }

pipeline{
    agent{
        node {
            label 'Agent-1'
        }
    }
    
    stages{
        stage('Build'){
            steps{
                echo 'Building'
            }
        }
    

        stage('Test'){
            steps{
                echo 'Testing'
            }
        }

        stage('Deploy'){
            steps{
                echo 'Deplying'
            }
        }
    }

    post{
        always{
            echo 'T will run always'
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
