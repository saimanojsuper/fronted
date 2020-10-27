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
        steps{
                   def sonarqubeScannerHome = tool name: 'sonar', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
                   withCredentials([string(credentialsId: 'sonar', variable: 'sonarLogin')]) {
                   sh "${sonarqubeScannerHome}/bin/sonar-scanner -e -Dsonar.host.url=http://3.94.115.145:9000 -Dsonar.login=${sonarLogin} -Dsonar.projectName=sonar-test -Dsonar.projectVersion=${env.BUILD_NUMBER} -Dsonar.projectKey=GS -Dsonar.sources=test/ "
                   }
             }
        }
    }
}
