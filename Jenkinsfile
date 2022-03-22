pipeline{
    agent any
    parameters {
        string(name: 'DEPLOY_ENV', defaultValue: 'staging', description: '')
        booleanParam(name: 'DEBUG_BUILD', defaultValue: true, description: '')
        choice(name: 'CHOICES', choices: ['one', 'two', 'three'], description: '')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'A secret password')
    }
    environment {
        NAME = "Abhishek"
        version = "1.0.0"
    }
    stages{
        stage("Build"){
            steps{
                echo "Building the application"
                echo "NAME ${NAME}"
                echo "Version ${version}"
                echo "Build No ${BUILD_NUMBER}"
                echo "${params.DEPLOY_ENV}"
                echo "Choice: ${params.CHOICES}"
                echo "Choice: ${params.DEBUG_BUILD}"
                echo "Choice: ${params.PASSWORD}"
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
            parallel {
                stage('Branch A') {
                    steps {
                        echo "On Branch A"
                    }
                }
                stage('Branch B') {
                    steps {
                        echo "On Branch B"
                    }
                }
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