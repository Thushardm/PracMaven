pipeline{
	agent any
	
	tools{
		maven 'Maven'
		gradle 'Gradle'
		jdk 'JDK'
	}
	
	stages{
		stage('Checkout'){
			steps{
				git branch:'master', url:'https://github.com/Thushardm/PracMaven.git'
			}
		}
		
		stage('Build'){
			steps{
				sh 'mvn clean package'
			}
		}
		
		stage('Run'){
			steps{
				sh 'mvn exec:java -Dexec.mainClass=com.example.App'
			}
		}
	}
	
	post{
		success{
			echo 'Successful'
		}
		failure{
			echo 'Failed'
		}
	}
}
