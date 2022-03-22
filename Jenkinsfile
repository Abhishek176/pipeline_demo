pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "Building the application"
            }
        }
        stage("Test"){
            steps{
                echo "Testing the application"
                sh "touch1 a.txt"
            }
        }
        stage("Deploy"){
            steps{
                echo "Deploying the application"
            }
        }
        stage("testing hook"){
            steps{
                echo "Testing webhook"
            }
        }
    }
    post{
        always{
            echo "====++++always++++===="
        }
        success{
            echo "====++++only when successful++++===="
        }
        failure{
            echo "====++++only when failed++++===="
        }
    }
}