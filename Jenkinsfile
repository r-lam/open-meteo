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
            sh 'curl -LO https://dl.k8s.io/release/v1.26.2/bin/linux/amd64/kubectl'  
            sh 'chmod u+x ./kubectl' 
            sh './kubectl apply -f deployment.yaml'
          }
        }
      }
    }
  }
}