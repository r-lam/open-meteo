pipeline {
  agent {
    kubernetes {
      	cloud 'kubernetes'
      	label 'default'
      	defaultContainer 'jnlp'
      }
    }
  stages {
    stage('Deploy App') {
      steps {
        script {
          withKubeConfig([credentialsId: 'eks1', serverUrl: 'https://kubernetes.default']) {
            sh 'kubectl apply -f deployment.yaml'
          }
        }
      }
    }
  }
}