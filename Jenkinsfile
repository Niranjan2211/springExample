pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '/opt/maven/bin/mvn clean'
      }
    }
    stage('Test') {
      steps {
        sh '/opt/maven/bin/mvn test'
      }
    }
    stage('Deploy') {
      steps {
        sh '/opt/maven/bin/mvn package'
      }
    }
    stage('report') {
      steps {
        cucumber fileIncludePattern: '**/*.json', sortingMethod: 'ALPHABETICAL'
      }
    }
  }
}
