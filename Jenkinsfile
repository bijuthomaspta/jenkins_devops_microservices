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
			      sh 'docker --version'
         }
}

                 stage('Build') {
                           steps {
                              sh "mvn clean compile"
         }
}
//                 stage('Test') {
//                            steps {
//                               sh "mvn test"
//          }
// 			   post {
//                                always {
//                                     junit 'target/surefire-reports/*.xml' 
// 			       }
// 			   }
// }
                stage('Integration Test') {
                           steps {
                              sh "mvn failsafe:integration-test failsafe:verify"
         }
}
                 stage('package') {
                           steps {
                              sh "mvn package -DskipTests"
         }
}
		stage('Build Docker Image'){
                           steps {
				   script{
					   docker.build("bijuthomaspta / currency-exchange-devops:400")
				         }
         }
}
		stage('Push Docker Image') {
                           steps {
				   script{
					   docker.withRegistry('', 'dockerhub') { 
						   dockerImage.push();
						   dockerImage.push(latest);
					   }
				   }
			   }
         }
 }
}
