pipeline {
	agent { label 'tomcat-slave' }
	
	stages {
		stage ('Git Checkout') {
			steps {
				git branch: 'master', url: 'https://github.com/smitaniusha/javacodes.git'
			}
		}
		stage ('Build') {
			steps {
				sh 'mvn clean install'
			}
		}
		stage ('Push to artifactory') {
			steps {
				sleep 5
			}
		}
		stage ('Deploy') {
			steps {
				sh 'sudo cp /home/ec2-user/jenkins-slave1/workspace/demopipe/target/*.war /opt/apache-tomcat-9.0.64/webapps/'
			}
		}
	}
}
