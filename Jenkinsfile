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
     
    stage('SonarQube analysis') {
      steps {
        script {
          def sonarqubeScannerHome = tool name: 'sonar', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
        }
        withSonarQubeEnv('SonarQube Scanner') {
          sh "${sonarqubeScannerHome}/bin/sonar-scanner -e -Dsonar.host.url=http://18.234.237.49:9000 -Dsonar.login=${sonarLogin} -Dsonar.projectName=sonar-test -Dsonar.projectVersion=${env.BUILD_NUMBER} -Dsonar.projectKey=GS -Dsonar.sources=test/  "
     
           }
        }
      }
  
    }
}
