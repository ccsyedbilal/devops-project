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
        sh 'apt install nodejs && apt install npm'
      }
    }

    stage("build"){
      steps{
        sh 'bun run build'
      }
      
    }
  }
}
