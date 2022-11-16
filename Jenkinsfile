pipeline {
  agent {
    kubernetes {
        yamlFile 'build-pods.yaml'
    }
  }
  stages {
    stage('Build') {
      steps {
        git branch: 'main', url: 'https://github.com/fabiogoma/spring-petclinic'
        container('maven') {
          sh 'mvn -B -ntp clean package'
        }
      }
    }
  }
}
