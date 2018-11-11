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
        bat 'echo "Deploying"'
      }
    }
    stage('Result') {
      steps {
        archiveArtifacts 'target/*war'
      }
    }
  }
}