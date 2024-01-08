pipeline {
    agent any
    
    environment {
        NODEJS_VERSION = '14.17.3'  // Update with the desired Node.js version
        NPM_REGISTRY = 'https://registry.npmjs.org/'
        DOCKER_REGISTRY = 'your.docker.registry'
        DOCKER_IMAGE_NAME = 'your-docker-image-name'
        DOCKER_IMAGE_TAG = 'latest'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install dependencies') {
            steps {
                script {
                    def npmCommand = "${tool 'Node.js'} /usr/local/bin/npm"
                    bat "npm install"
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    def npmCommand = "${tool 'Node.js'} /usr/local/bin/npm"
                    bat "npm run build"
                }
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
