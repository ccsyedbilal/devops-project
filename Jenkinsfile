pipeline {
  agent any
  stages {
    stage("Test"){
      steps{
        sh 'npm install -g bun'
        sh 'bun -v'
      }
    }

    stage("build"){
      steps{
        sh 'bun run build'
      }
      
    }
  }
}
