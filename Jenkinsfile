pipeline{
	agent any
	tools{
		maven 'Maven'
	}
	stages{
		stage('Checkout'){
			steps{
				git branch : 'master' , url : 'https://github.com/ThisisRishavKumar/Maven_App.git'
			}
		}
		stage('Build') {
			steps{
				sh 'mvn clean package'
			}
		}
		stage('Test') {
			steps {
				sh 'mvn test'
			}
		}
		
		stage('Run Application'){
			steps {
				sh 'java -jar target/Maven_App-1.0-SNAPSHOT.jar'
			}
		}
	}
	post {
		success {
			echo 'Successfuly deployed'
		}
		failure{
			echo 'Error in Deployment'
		}
	}
}
