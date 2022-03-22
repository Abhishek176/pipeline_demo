pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "Building the application"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo "========A executed successfully========"
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
        stage("Test"){
            steps{
                echo "Testing the application"
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