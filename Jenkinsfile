pipeline {
    agent any
	tools {
		maven 'Maven3'
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
        stage('docker build & push') {
            steps {
                script{
                withDockerRegistry(credentialsId: 'd99ce8e5-4954-4982-b967-ec92b9f2a070') {
                    sh "docker build -t hemasruthireddyj/gitpro:tag123 ."
                    sh "docker push hemasruthireddyj/gitpro:tag124"
}
}
                }
                
            }
        }
		
    }

