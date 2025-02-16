pipeline {
    agent any
    environment {
        PATH = "/opt/maven/bin:$PATH"
    }
    stages {
        stage('Build') {
            steps { 
                sh 'mvn clean install'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonar server') {
                    sh "${tool 'sonar scanner'}/bin/sonar-scanner"
                }
            }
        }
    }
}
