pipeline {
    agent any
    parameters([
        choice(
            choices: ['v1', 'v2', 'v3'],
            name: 'version'
        )

    ])
    docker {
        image 'node:18-alpine'
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Build disparado pelo Git! pt 3'
                sh 'ls -la'
            }
        }
        stage('Build') {
            steps {
                echo 'Simulando build...'
                sh "echo $version > versao.txt"
            }
        }
        stage('Test') {
            steps {
                sh 'cat versao.txt'
            }
        }
    }
    post {
        always {
            cleanWs()
        }
    }
}