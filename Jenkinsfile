pipeline {
  agent {
    docker {
      image 'your-jenkins-image'
      args '-v /var/run/docker.sock:/var/run/docker.sock' // Mount the Docker socket
    }
  }
  stages {
    stage("Test") {
      steps {
        script {
          // Use Docker to install packages on the host machine
          sh 'docker run --rm -v /var/run/docker.sock:/var/run/docker.sock debian apt update && docker run --rm -v /var/run/docker.sock:/var/run/docker.sock debian apt install -y nodejs npm unzip'
          sh 'curl -fsSL https://bun.sh/install | bash'
          sh 'npm install -g bun'
        }
      }
    }

    stage("build") {
      steps {
        sh 'bun run build'
      } 
    }
  }
}
