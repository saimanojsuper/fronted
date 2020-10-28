pipeline {
  agent any
  tools {nodejs "node"}
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
      stage('Test') {
                    steps {
                        echo 'test started'
                        echo 'test ended'
                    }
                }
     
    stage('sonar-scanner') {
      steps {
        script {
          sonarqubeScannerHome = tool name: 'sonar', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
        }
        withSonarQubeEnv('sonar') {
          sh "${sonarqubeScannerHome}/bin/sonar-scanner "
     
           }
        }
      }
  
    }
}
