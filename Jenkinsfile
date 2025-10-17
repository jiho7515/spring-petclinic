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
    
    // Docker Image 생성
    stage('Docker Image Build') {
    steps {
        dir("${env.WORKSPACE}") {
          sh """
            docker build -t wlgh7515/spring-petclinic:$BUILD_NUMBER .
            docker tag wlgh7515/spring-petclinic:$BUILD_NUMBER wlgh7515/spring-petclinic:latest
            """
        }
      }
    }
    
  }
}
