pipeline {
  agent any
  
  stages {
    stage('SCM') {
      steps{
        checkout scm
      } 
    }
    stage('SonarQube Analysis') {
      steps{
        def mvn = tool 'M3';
        withSonarQubeEnv() {
        sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=toto-gros -Dsonar.projectName='toto-gros'"
      }
    }
     
  }
 }
}
