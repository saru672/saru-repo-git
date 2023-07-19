pipeline {
	agent {
	label "built-in"
	}
	stages {
		stage-1 ('create container') {
			steps {
			sh " docker run -itdp 80:80 --name my-container-23Q1 httpd"
			}
		}	
		stage-2 ('deploy') {
			steps { 
			sh " docker cp index.html my-container-23Q1:usr/local/apache2/htdocs/"
			}
		}
	}
}
