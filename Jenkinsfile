pipeline {
	agent {
	label "built-in"
	}
	stages {
		stage ('create container') {
			steps {
			sh "docker stop my-container-23Q2 "
			sh "docker rm my-container-23Q2"
			sh " docker run -itdp 81:80 --name my-container-23Q2 httpd"
			}
		}	
		stage ('deploy') {
			steps {
			sh " docker cp index.html my-container-23Q2:/usr/local/apache2/htdocs"
			sh " docker exec my-container-23Q2 chmod -R 777 /usr/local/apache2/"
			}
		}
	}
}
