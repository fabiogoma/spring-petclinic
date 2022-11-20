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
          // sh 'mvn -B -ntp package'
          sh 'mvn -B package'
          sh "find . -name '*.xml'"
        }
      }
    }
  }
  post {
    always {
      junit 'target/surefire-reports/*.xml'
    }
  }
}
