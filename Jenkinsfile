environment {
    MAVEN_HOME = tool 'Maven'
}
pipeline {
  agent {
    label 'king'
  }
  stages {
    stage('checkout') {
      steps {
        sh 'rm -rf  bus_booking'
        sh 'https://github.com/sudhasanshi/weather-update.git'
      }
    }
    stage('build') {
      steps {
        sh '${MAVEN_HOME}/bin/mvn clean package'
      }
    }
    stage('Run Locally') {
      steps {
        sh '${MAVEN_HOME}/bin/mvn clean package'
        sh 'java -jar target/myhealthapp.jar &'
      }
    }
  }
}
