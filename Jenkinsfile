pipeline {
    triggers {
  pollSCM('* * * * *')
    }
   agent any
    tools {
  maven 'M2_HOME'
}
    stages {

        stage("build & SonarQube analysis") {          
            steps {
                dir('./fastfood_backend/'){
                    withSonarQubeEnv('SonarServer') {
                        sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=kaka-gitng_fastfoodtest'
                        }
                }
            }
          }
    }
}