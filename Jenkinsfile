pipeline {

    agent {
        docker {
            image 'node:18-alpine'
        }
    }
    
    parameters {
        choice(
            name: 'version',
            choices: ['v1', 'v2', 'v3'],
            description: 'Escolha a versão'
        )
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
                sh "echo ${params.version} > versao.txt"
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