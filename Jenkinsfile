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

        stage('Test Log') {
          steps {
            writeFile(file: 'LogTestFile.txt', text: 'This is an automation file log')
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        when {
          branch 'master'
        }
        stage('Deploy') {
          steps {
            input(message: 'Do you want to Deploy?', id: 'OK')
            echo 'Deploying the app in IIS server'
          }
        }

        stage('Artifacts') {
          steps {
            archiveArtifacts 'LogTestFile.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = 'E:\\Personal\\1.DevOps_darey\\Apps_installs\\chromedriver_win32\\chromedriver.exe'
  }
}