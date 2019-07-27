pipeline {
  agent any
  stages {
    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace... */
      steps {
        checkout scm
      }
    }
    stage('Build Project and Generate Docker Images') {
      steps {
        sh 'mvn -B -DskipTests clean package'
        sh 'echo $USER'
        sh 'echo whoami'
      }
    }
    stage('Run eureka application') {
      steps {
              sh 'java -jar eureka-registry-service/target/eureka-registry-service-0.0.1-SNAPSHOT.jar > yourservice.log 2>&1'
            }
    }
  }
}
