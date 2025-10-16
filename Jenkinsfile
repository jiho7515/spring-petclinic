pipeline {
  agent any

  tools {
    maven 'M3'
    jdk 'JDK21'
  }

  stages {
    // Github Clone
    stage('Git Clone') {
      steps {
        git url: 'https://github.com/jiho7515/spring-petclinic.git/', branch: 'main'
      }
    }

    //Maven Build
    stage('Maven Build') {
      steps {
        sh 'mvn -Dmaven.test.failure.ignore=true clean package'
      }
    }
  }
}
