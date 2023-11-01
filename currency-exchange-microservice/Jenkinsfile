

//Declarative
pipeline {
	agent any
	
	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'my-maven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"+"/currency-exchange-microservice"
	}

	stages{
	      stage('Checkout'){
		steps{
			sh 'mvn --version'
			sh 'docker version'
			echo "Build"
		}
	      }
	      stage('Compile'){
		steps{
			sh 'mvn clean compile'
		}
	      }
	      stage('Test'){
		steps{
			sh 'mvn test'
		}
	      }
	}
	post{
		always{
			echo 'im awesome. i run always.'
		}
		success{
			echo 'i run when you are successfull.'
		}

		failure{
			echo 'i run when you fail.'
		}
	}


	
}
