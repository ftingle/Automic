pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sleep 30
      }
    }
    stage('Test') {
      parallel {
        stage('Test Windows') {
          steps {
            bat(script: 'Test.bat', returnStatus: true)
          }
        }
        stage('Test Linux') {
          steps {
            sh 'test.sh'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        mail(subject: 'Testing Complete', body: 'testing has been successful', cc: 'frank.tingle.uk@gmail.com', from: 'frank.tingle@gmail.com')
      }
    }
  }
}