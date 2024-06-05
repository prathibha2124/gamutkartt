pipeline {
    agent any

    stages {
        stage('Clone-Repo') {
	    	steps {
	        	checkout scm
	    	}
        }
	/* stage ('Build'){
	        steps {
			sh 'mvn clean install'
                }
	}

	stage('Run Tests') {
	    steps {
	       sh 'mvn test'
	    }
	} */

        stage('Package as WAR') {
            steps {
                sh 'mvn package'
            }
        }
	stage('Deployment') {
	   steps {
		sh 'scp /root/var/lib/jenkins/workspace/gamutkart-demo/target/gamutkart.war @10.128.0.4:/home/kiranv2111/tomcat/apache-tomcat-9.0.89/webapps' 
	   }
    } */
}
}
