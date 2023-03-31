pipeline {
	agent { docker { image 'maven:3.63'}}
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
