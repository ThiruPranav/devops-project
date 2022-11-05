pipeline {
	agent {
		label ('master')
	}

    stages {
        stage('scm') {
            steps {
               git 'https://github.com/ThiruPranav/devops-project.git'
            }
        }
		stage('build') {
            steps {
               sh 'mvn clean package'
            }
        }
		stage('deploy') {
            steps {
               deploy adapters: [tomcat9(credentialsId: 'tomcat_Credentials', path: '', url: 'http://10.0.0.91:8080/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
