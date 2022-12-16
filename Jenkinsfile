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
            echo '"Get the DriverPath ${ChromeDriverPath}"'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'Do you want to Deploy?', id: 'OK')
        echo 'Deploying the app in IIS server'
      }
    }

  }
  environment {
    ChromeDriverPath = 'E:\\Personal\\1.DevOps_darey\\Apps_installs\\chromedriver_win32\\chromedriver.exe'
  }
}