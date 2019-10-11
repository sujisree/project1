pipeline {
    agent any
    stages {

        stage('clean') {
            steps {
                sh "mvn clean "
            }
        }
       
        stage('validate') {
            steps {
                sh "mvn validate "
            }
        }
       
        stage('build') {
            steps {
                sh "mvn package "
            }
        }
        stage('deploy') {
            steps {
                sh "scp -r ubuntu@172.31.91.11:/var/lib/jenkins/workspace/test-git/target/maven-1.0.jar ubuntu@172.31.47.183:/workspace/tomcat/
            }
        }
    }
}
