pipeline {
	agent { docker { image 'node:13.8'} }
	stages {
		stage('Build'){
			steps{
				echo "Build"
				sh 'mvn --version'
			}
		}
		
		
	}
}
