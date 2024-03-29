pipeline {
    agent any

    stages {
        stage('Clone-Repo') {
	    	steps {
	        	checkout scm
	    	}
        }
	 stage ('Build'){
	        steps {
			sh 'mvn clean install'
                }
	}

	stage('Run Tests') {
	    steps {
	       sh 'mvn test'
	    }
	}

        stage('Package as WAR') {
            steps {
                sh 'mvn package'
            }
        }
	stage('Deployment') {
	   steps {
		sh 'scp /root/.jenkins/workspace/gamutkart-demo/target/gamutkart.war ubuntu@172.31.36.210:/opt/tomcat/apache-tomcat-10.1.19/webapps' 
	   }
    }
}
}
