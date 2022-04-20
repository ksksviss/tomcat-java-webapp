pipeline {
    agent any

    tools {
        maven "maven3"
    }

    stages {
        stage('Build') {
            steps {

                sh "mvn clean package sonar:sonar -Dsonar.host.url=http://192.168.56.102:9000"
            }
        }
		stage('imagebuild') {
			steps {
				
				sh "docker build -t ksksviss/tomcatjavaapp ."
			}
		}
		stage('publishimage') {
			steps {
				
				sh "docker push ksksviss/tomcatjavaapp"
			}
		}
    }
}
