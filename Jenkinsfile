pipeline {
  agent any

  stages {
    // Github Clone
    stage('Git Clone') {
      steps {
        git url: 'https://github.com/jiho7515/spring-petclinic.git/', branch: 'main'
      }
    }
  }
}
