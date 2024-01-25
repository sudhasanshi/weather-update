pipeline {
    agent {
        label 'sudha'
    }
    stages {
        stage('checkout') {
            steps {
                sh 'rm -rf weather-update'
                sh 'git clone https://github.com/sudhasanshi/weather-update.git'
            }
        }

        stage('build') {
            steps {
                script {
                    sh 'mvn --version'
                    sh 'mvn clean install'
                }
            }
        }

        stage('Show Contents of target') {
            steps {
                script {
                    // Print the contents of the target directory
                    sh 'ls -l target'
                }
            }
        }
        
        stage('deploy') {
            steps {
             
                sh "cp /home/sudha/workspace/weather-app/target/weather-forecast-app-1.0-SNAPSHOT.jar /opt/apache-tomcat-8.5.98/webapps/"
            }
        }
        
    }
        
    post {
        success {
            echo "Build, Run, and Deployment to Tomcat successful!"
        }
        failure {
            echo "Build, Run, and Deployment to Tomcat failed!"
        }
    }
}
