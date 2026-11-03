pipeline {
  agent any
  stages {
    stage('BUILD') {
      steps {
        bat 'docker --version && docker build -t newimg .'
      }
    }

    stage('RUN') {
      steps {
        bat 'docker rm -f newlab >nul 2>&1 & docker run -d -p 8081:80 --name newlab newimg'
      }
    }

    stage('VERIFY') {
      steps {
        bat 'docker ps'
      }
    }

  }
}