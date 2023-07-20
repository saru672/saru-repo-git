pipeline {
	agent {
	label "built-in"
	}
	stages {
		stage ('create container') {
			steps {
			sh " docker run -itdp 90:80 --name my-container-23Q3 httpd"
			}
		}	
		stage ('deploy') {
			steps {
			sh " docker cp index.html my-container-23Q3:/usr/local/apache2/htdocs"
			sh " docker exec my-container-23Q3 chmod -R 777 /usr/local/apache2/"
			}
		}
	}
}
