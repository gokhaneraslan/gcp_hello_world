pipeline {
  agent any
  stages {
    stage('Checkout Code') {
      steps {
        git(url: 'https://github.com/gokhaneraslan/gcp_hello_world', branch: 'main')
      }
    }

    stage('log') {
      parallel {
        stage('log') {
          steps {
            sh 'ls -la'
          }
        }

        stage('Front-End Unit Test') {
          steps {
            sh 'cd gcp_hello_world && pip3 install -r requirements.txt && uvicorn main.app:app'
          }
        }

      }
    }

  }
}