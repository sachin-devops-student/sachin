pipeline{
    agent any
    environment{
        PATH = "/opt/maven/bin:$PATH"
    }
    stages{
        stage('build'){
            steps{ 
                sh 'mvn clean deploy'
            }
        }
              stage('sonarqube analysis'){
               environment{
                scannerHom = tool 'sonar scanner'
}
            steps{
              with SonarQubeEnv('sonar server'){
              sh "${sonarHome}/bin/sonar scanner"
           }
       }
     }
  }
}
