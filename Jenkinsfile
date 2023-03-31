pipeline {
	agent label { docker { image 'maven:3.6.3' } }
	stages {
		stage('Build'){
			steps{
				echo "Build"
				sh 'mvn --version'
			}
		}
		
		stage('Test'){
			steps{
				echo "Test"
			}
		}
		stage('Integration Test'){
			steps{
				echo "Integration Test"
			}
		}
		
	}
}
