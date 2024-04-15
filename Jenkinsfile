pipeline {
  agent any
  stages {
    

    stage("Test"){
      steps{
        sh 'sudo apt update'
        sh 'sudo apt install nodejs && sudo apt install npm'
        sh 'sudo apt install unzip'
        sh 'curl -fsSL https://bun.sh/install | bash'
        sh 'npm install -g bun'
      }
    }

    stage("build"){
      steps{
        sh 'bun run build'
      }
      
    }
  }
}
