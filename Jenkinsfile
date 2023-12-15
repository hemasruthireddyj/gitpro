pipeline {
    agent any
	tools {
		maven 'mvn3'
        jdk 'OpenJDK8'
	}

    stages {
        stage('Build the source code using maven') {
            steps {
                echo 'mvn clean package'
            }
        }
		
		stage('git checkout') {
            steps {
               git branch: 'main', credentialsId: 'd99ce8e5-4954-4982-b967-ec92b9f2a070', url: 'https://github.com/hemasruthireddyj/gitpro'
            }
        }
		
    }
}
