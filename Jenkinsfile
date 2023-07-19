pipeline {
	agent {
	label "built-in"
	}
	stages {
		stage ('create container') {
			steps {
			sh " docker run -itdp 80:80 --name my-container-23Q1 httpd"
			}
		}	
		stage ('deploy') {
			steps { 
			sh " docker cp index.html my-container-23Q1:/usr/local/apache2/htdocs/"
			sh " chmod -R 777 /usr/local/apache2/htdocs"
			}
		}
	}
}
