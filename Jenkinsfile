pipeline {
  agent any
  tools {
    maven 'Maven3'
  }
  stages {
    stage('Clone') { step {
        git branch: 'master', url: 'https://github.com/NaiEang/AST-lab9.git'
    }}
  }
  stages {
    stage('Build')  { steps { sh 'mvn clean package' } }
    stage('Test')   { steps { sh 'echo "test the project"' } }
    stage('Package'){ steps { sh 'echo "package the project"' } }
  }
  post {
    always  { echo '**/target/surefire-reports/*.xml' }
    success { echo '✔ Pipeline green' }
    failure { echo '✗ Build failed' }
  }
}