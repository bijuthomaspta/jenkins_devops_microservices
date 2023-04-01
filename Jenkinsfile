pipeline {
	agent any
        environment {
                dockerHome = tool 'Mydocker'
                 mavenHome = tool 'Mymaven'
                 PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
}
	stages {
		stage('Build'){
			steps{
				echo "Build"
                                sh 'mvn --version'
                                sh 'docker --version'
    echo "path-$path"
}
}
		
	}
}
