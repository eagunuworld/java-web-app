pipeline {
  agent { label 'numericAgent' }
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  environment {
    HEROKU_API_KEY = credentials('darinpope-heroku-api-key')
  }
  parameters { 
    string(name: 'APP_NAME', defaultValue: '', description: 'What is the Heroku app name?') 
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t darinpope/java-web-app:latest .'
      }
    }
    
  }

}
