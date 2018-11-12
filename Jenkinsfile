pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Build') {
      steps {
        withMaven(maven: 'M3') {
          bat 'mvn clean install'
        }

      }
    }
    stage('Deploy') {
      steps {
        bat 'mvn wildfly:redeploy -DappDplySrvr.host=127.0.0.1-DappDplySrvr.port=9990'
      }
    }
    stage('Result') {
      steps {
        archiveArtifacts 'target/*.war'
      }
    }
  }
}