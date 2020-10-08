pipeline {
  agent any
  tools {nodejs "node"}
    stages {
        stage('Build') {
            steps {
                bat 'npm install'
            }
        }
      stage('Test') {
                    steps {
                        echo 'test started'
                        bat 'npm run test'
                        echo 'test ended'
                    }
                }
      stage('Sonarqube'){
        steps{
          bat 'sonar-scanner'
        }
      }
    }
}
