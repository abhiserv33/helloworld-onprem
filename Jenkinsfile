pipeline {
	agent any
	
	stages {
		stage('Build') {
			steps {
				git url: 'https://github.com/abhiserv33/test-repo.git', branch: 'main', credentialsId: '23c36c5f-e294-4923-8190-873c62acbe17'
				bat "mvn -Dmaven.test.failure.ignore=true clean package"
			}
		}
		stage('Test') {
			steps {
				git url: 'https://github.com/abhiserv33/test-repo.git', branch: 'main', credentialsId: '23c36c5f-e294-4923-8190-873c62acbe17'
				bat "newman run https://www.getpostman.com/collections/d2482faa7d42210dc905 -r htmlextra"
			}
		}
		stage('Deploy') {
			steps {
				git url: 'https://github.com/abhiserv33/test-repo.git', branch: 'main', credentialsId: '23c36c5f-e294-4923-8190-873c62acbe17'
				bat "mvn -Dmaven.test.failure.ignore=true clean install deploy -DmuleDeploy"
			}
		}
		
		
	}
}
