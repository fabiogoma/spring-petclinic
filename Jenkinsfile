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
          sh 'mvn -B -ntp package'
          sh 'ls -ltr'
        }
      }
    }
  }
  post {
    always {
      junit '**/target/surefire-reports/*.xml'
    }
  }
}
