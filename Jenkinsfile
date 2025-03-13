pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/Surya-reddy-s/PES2UG22CS216_jenkins']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES2UG22CS216-1'
                sh 'g++ main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
           echo 'error Pipeline failed'
        }
    }
}