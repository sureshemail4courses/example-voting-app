pipeline {

  agent { label 'kubepod' }
  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/sureshemail4courses/example-voting-app.git', branch:'master'
      }
    }

    stage('Deploy App to k8s') {
      steps {
        script {
          kubernetesDeploy(configs: "k8s-specifications/apps/", kubeconfigId: "mykubeconfig")
        }
      }
    } 
  }

}
