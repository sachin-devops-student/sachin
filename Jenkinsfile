pipeline{
    agent any
    environment{
        PATH = "/opt/maven/bin:$PATH"
    }
    stages{
        stage('build'){
            steps{ 
                sh 'mvn clean install'
            }
        }
              stage('sonarqQube analysis'){
               environment{
                scannerHome = tool 'sonar scanner'
}
            steps{
              with SonarQubeEnv('sonar server'){
              sh "${scannerHome}/bin/sonar scanner"
           }
       }
     }
  }
}
