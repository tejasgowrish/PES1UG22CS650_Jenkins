pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    useRemoteConfigs: [[url: 'https://github.com/tejasgowrish/PES1UG22CS650_Jenkins.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                build 'pes1ug22cs650-1'
                sh 'g++ main/hello_world.cpp -o output'
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
            error 'Pipeline failed'
        }
    }
}
