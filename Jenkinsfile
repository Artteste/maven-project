pipeline {
  agent any
  tools {
    maven "LocalMaven"}
  stages {
    stage('Test') {
      steps {
        //sh 'mvn clean compile test'
        bat 'mvn clean compile test'
        echo "Testing is done"
      }
    }
    stage('Buildand Send Results to Sonar') {
      steps {
        withSonarQubeEnv(installationName: 'localSonar')}
      {
       // sh 'mvn package'
        bat ('mvn -B -DskipTests clean package sonar:sonar -Dsonar.login=admin -Dsonar.passsword=Admin')
      }
    }

  
        }

  }
}
