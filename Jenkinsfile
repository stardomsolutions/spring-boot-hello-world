pipeline {
    agent any

    tools {
        maven "maven3"
    }

    stages {
        stage('Build') {
            steps {

                sh "mvn clean package -Dmaven.test.skip=true"
            }
        }
		stage('Image Build') {
			steps {
				sh "docker build -t stardomsolutions/spring-boot-hello-world ."
				
			}
		}
		stage('Publish Image') {
			steps {
				sh "docker push stardomsolutions/spring-boot-hello-world"
			}
		}
    }
}
