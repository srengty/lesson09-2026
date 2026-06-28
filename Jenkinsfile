pipeline {
  agent any
  stages {
    stage('Package') {
      steps { 
        sh 'mvn -B clean package -DskipTests'
        @Library('itc-shared') _
          sayHello('World')
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