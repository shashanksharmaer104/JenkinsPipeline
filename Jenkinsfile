pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building Java code application'
          }
        }

        stage('Test') {
          steps {
            echo 'Testing the application'
            echo "Get chrome driver path ${ChromeDriverPath}"
          }
        }

        stage('Test Log') {
          steps {
            writeFile(file: 'LogTestFile.txt', text: 'This is an automated message')
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'Do you want to deploy?', id: 'OK')
        echo 'Deploying app in server'
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\driver\\Web\\chromedriver.exe'
  }
}