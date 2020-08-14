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

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying app in server'
        input(message: 'Do you want to deploy?', id: 'OK')
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:\\driver\\Web\\chromedriver.exe'
  }
}