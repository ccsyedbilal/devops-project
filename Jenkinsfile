pipeline {
  agent any
  stages {
    stage("checkout"){
      steps{
        checkout scm
      }
    }

    stage("Test"){
      steps{
        sh 'sudo apt install nodejs && sudo apt install npm'
        sh 'sudo apt install unzip'
        sh 'curl -fsSL https://bun.sh/install | bash'
      
      }
    }

    stage('Build') {
            steps {
                dir('/var/lib/jenkins/workspace/my_nextjs_app') {
                    sh 'bun install'
                }
            }
        }
      
    }
  }
}
