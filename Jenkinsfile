pipeline{
	agent any
	paramerters{
		string(
			name: 'BRANCH_NAME',
			defaultValue: 'main',
			description: 'Git branch to build'
		)
	}
	stages{
		stage('Checkout'){
			steps{
				git branch: paramas.BRANCH_NAME,
				url: 'https://github.com/dimpledimpu50-cmyk/pract/blob/main/Jenkinsfile'
			}
		}
		stage('Build'){
			steps{ sh 'mvn clean package' }
		}
		stage('Test'){
			steps{ sh 'mvn test' }
		}
	}
	post{
		success{
			archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
}
}
}
