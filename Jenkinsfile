pipeline {
  agent any
  stages {
    stage("checkout"){
      steps{
        check nextjs
      }
    }

    stage("Test"){
      steps{
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
