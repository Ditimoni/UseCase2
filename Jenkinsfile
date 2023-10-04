pipeline {
    agent any 
    stages {
	stage('checkout') {
		steps{
    		git 'https://github.com/Ditimoni/UseCase2.git'
	}
    	}
        stage('build and test') {
steps{
    		bat 'mvn clean package'
   	}
}
        stage('Deploy') { 
steps{
                  deploy adapters: [tomcat9(credentialsId: 'tomcat-manager-scripts', path: '', url: 'http://localhost:9080')], 
contextPath: '/usecase2', war: '**/*.war'
        }
}
   } 
}
