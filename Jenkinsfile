@Library('itc-shared') _
pipeline {
  agent any
  stages {
    stage('Welcome') {
        steps {
          sayHello('World')
        }
    }
    stage('Package') {
      steps { 
        bat 'mvn -B clean package -DskipTests'
      }
      post {
        success {
          archiveArtifacts artifacts: 'target/*.war',
                           fingerprint: true,
                           onlyIfSuccessful: true
          
        }
      }
    }
  }
}