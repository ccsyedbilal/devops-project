pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Check if dependencies are installed
                    def nodejsInstalled = sh(script: 'command -v nodejs', returnStatus: true) == 0
                    def npmInstalled = sh(script: 'command -v npm', returnStatus: true) == 0
                    def unzipInstalled = sh(script: 'command -v unzip', returnStatus: true) == 0
                    def bunInstalled = sh(script: 'command -v bun', returnStatus: true) == 0

                    if (!nodejsInstalled || !npmInstalled || !unzipInstalled || !bunInstalled) {
                        echo 'Missing dependencies. Installing...'
                        sh 'sudo apt update && sudo apt install -y nodejs npm unzip'
                        sh 'curl -fsSL https://bun.sh/install | sudo bash'
                    } else {
                        echo 'All dependencies are already installed.'
                    }
                }
            }
        }

        stage('Test') {
            steps {
                // Your testing steps here
            }
        }

        stage('Build') {
            steps {
                // Your build steps here, assuming bun is available
                sh 'bun run build'
            }
        }

        // Add more stages as needed
    }
}
