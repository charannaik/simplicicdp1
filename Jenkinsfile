pipeline {
	agent any
    	tools {
		maven 'mymaven'
    }
    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/charannaik/cicdproject1.git', branch: 'main'
            }
        }  
        stage('Compile') {
            agent { label 'slave1' }
            steps {
		sh "mvn compile"
            }
        }
        stage("Unit test"){
            agent { label 'slave2' }
            steps{
		sh "mvn test"
            }
        }
    }
}
