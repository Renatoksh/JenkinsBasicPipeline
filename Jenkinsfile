pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building .NET Core application'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the application'
          }
        }

        stage('Deploy') {
          steps {
            echo 'Deploying the app in IIS server'
          }
        }

      }
    }

  }
}