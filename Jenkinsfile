node('Node') {
	stages {
		stage('Build') {
			steps {
				git 'https://github.com/abhiserv33/test-repo.git'
				bat "mvn -Dmaven.test.failure.ignore=true clean package"
			}
		}
		
		stage('Test') {
			steps {
				git 'https://github.com/abhiserv33/test-repo.git'
				bat "mvn -Dmaven.test.failure.ignore=true clean test"
			}
		}
		
		stage('Deploy') {
			steps {
				git 'https://github.com/abhiserv33/test-repo.git'
				bat "mvn -Dmaven.test.failure.ignore=true clean install deploy -DmuleDeploy"
			}
		}
	}
}
