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
                echo Deploying..'
		sh 'mvn deploy'
	    }	
        }
    }
}
