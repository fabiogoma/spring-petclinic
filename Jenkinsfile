pipeline {
  agent {
    kubernetes {
        yamlFile 'build-pods.yaml'
    }
  }
  stages {
    stage('Build') {
      steps {
        container('maven') {
          sh 'mvn -B -ntp clean package'
        }
      }
    }
  }
}
