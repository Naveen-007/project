pipeline {
    agent any

    stages {
        stage('validate') {
            steps {
                echo 'validating..'
		sh 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
		sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sshagent(['tomcat']) {
                   scp "ssh -o StrictHostKeyChecking=no 04-deploy/target/WebAppCal-1.2.8.war centos@http://3.237.204.59/:/home/centos/apache-tomcat-7.0.94/webapps
                } 
            }
        }
    }
}
