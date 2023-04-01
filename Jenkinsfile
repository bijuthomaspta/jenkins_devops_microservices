pipeline {
	agent any
        environment {
                dockerHome = tool 'Mydocker'
                 mavenHome = tool 'Mymaven'
                 PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
}
	stages {
		stage('checkout') {
                           steps {
                              sh 'mvn --version '
         }
}

                 stage('compile') {
                           steps {
                              sh "mvn clean compile"
         }
}
                stage('Test') {
                           steps {
                              sh "mvn test"
         }
}
                stage('Integration Test') {
                           steps {
                              sh "mvn failsafe:integration-test failsafe:verify"
         }
}


		
	}
}
