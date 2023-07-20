pipeline {
	agent {
	label "built-in"
	}
	stages {
		stage ('create container') {
			steps {
			sh "docker stop my-container-23Q1 "
			sh "docker rm my-container-23Q1"
			sh " docker run -itdp 80:80 --name my-container-23Q1 httpd"
			}
		}	
		stage ('deploy') {
			steps {
			sh " docker cp index.html my-container-23Q1:/usr/local/apache2/htdocs"
			sh " docker exec my-container-23Q1 chmod -R 777 /usr/local/apache2/"
			}
		}
	}
}
