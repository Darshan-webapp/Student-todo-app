pipeline {
  agent any

  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/Darshan-webapp/Student-todo-app.git'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t student-todo-app .'
      }
    }

    stage('Run Container') {
      steps {
        sh 'docker stop student-todo || true'
        sh 'docker rm student-todo || true'
        sh 'docker run -d --name student-todo -p 8080:80 student-todo-app'
      }
    }
  }
}