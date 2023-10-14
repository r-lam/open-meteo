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
          kubernetesDeploy(configs: "deployment.yaml")
        }
      }
    }
  }
}