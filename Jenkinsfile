pipeline {
    agent any
    stages {
        stage("Clean Up"){
            steps {
                deleteDir()
            }
        }
        stage("Clone Repo"){
            steps{
                sh "git clone https://github.com/jenkins-docs/simple-java-maven-app.git"
            }
        }
        stage("Build"){
            steps{
                dir("simple-java-maven-app"){
                    sh "mvn clean install -Denforcer.skip=true"
                }
            }
        }
        stage("Test"){
            steps {
                dir("Simple-java-maven-app"){
                    sh "mvn test -Denforcer.skip=true"
                }
            }
        }
    }
}