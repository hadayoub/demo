pipeline {
    agent any
    tools {
        maven 'Maven 3.8.4'
        jdk 'jdk9'
    }
    stages {
        stage ('Build') {
            steps {
                sh 'mvn clean install' 
            }
            post {
                success {
                	sh '''
                		echo "success"
                	'''
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}
