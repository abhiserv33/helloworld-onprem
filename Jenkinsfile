pipeline {
	agent any
	
	stages {
		
		
		stage('Test') {
			steps {
				git url: 'https://github.com/abhiserv33/test-repo.git', branch: 'main', credentialsId: '23c36c5f-e294-4923-8190-873c62acbe17'
				bat "newman run https://www.getpostman.com/collections/d2482faa7d42210dc905 -r htmlextra"
			}
		}
	}
	
	post {
        	always {
            		emailext body: 'A Test Email', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
        }
    }
}
