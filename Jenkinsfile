pipeline {
    agent any
    stages{
        stage('checkout'){
            steps{
                deleteDir()
                git 'https://github.com/bharath0080/simple-java-maven-app.git'
            }
        }
        stage('build'){
            steps{
                withSonarQubeEnv('testSonar') {
                sh 'mvn clean package sonar:sonar’
                //the below two line are if u are executing sonarqube using sonarscanner commandline
                //sh "mvn clean install" 
                //sh "/app/home/mradmin/.jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/testScanner/bin/sonar-scanner -Dsonar.projectKey=com.mycompany.app:my-app -Dsonar.sources=. -Dsonar.java.binaries=target/classes"  
              }
            }
        }
    }
}
