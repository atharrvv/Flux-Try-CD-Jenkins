pipeline {
  agent any 

  stages {
    stage ('Docker Build') {
      steps { 
        script {
          docker.build('eatherv/python-application:0.0.4', './Dockerfile')
        }
      }
      stage ('Docker Push') {
        steps {
          script {
            docker.withRegistry('https://index.docker.io/v1/', 'docker') {
              docker.image("eatherv/python-application:0.0.4").push()
            }
          }
        }
      }
    }
  }
}
