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
