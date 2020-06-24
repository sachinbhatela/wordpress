pipeline {

  agent { label 'jenkins-jenkins-slave' }


  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/sachinbhatela/wordpress.git', branch:'mysql'
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
