pipeline {

  agent { label 'jenkins-jenkins-slave' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/sachinbhatela/wordpress.git', branch:'pod'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "deployment.yml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}
