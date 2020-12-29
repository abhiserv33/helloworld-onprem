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
			mail bcc: '', body: "<b>Example</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "abhinav.sarkar@apisero.com.com";        }
    		}
	}
}
