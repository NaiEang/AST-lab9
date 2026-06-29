pipeline {
  agent any
  tools {
    maven 'Maven3'
  }
  stages {
    stage('Build')  { steps { sh 'echo "build the project"' } }
    stage('Test')   { steps { sh 'echo "test the project"' } }
    stage('Package'){ steps { sh 'echo "package the project"' } }
  }
  post {
    always  { echo '**/target/surefire-reports/*.xml' }
    success { echo '✔ Pipeline green' }
    failure { echo '✗ Build failed' }
  }
}