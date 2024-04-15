pipeline {
  agent any
  stages {
    stage("Test"){
      steps{
        sh 'apt install nodejs && apt install npm'
        sh 'apt install unzip'
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
