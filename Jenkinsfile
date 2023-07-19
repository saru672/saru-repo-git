pipeline {
	agent {
	label "built-in"
	}
	stages {
		agent {
			docker {image 'httpd'}
		}
		stage ('create container') {
			steps {
			sh " docker run -itdp 80:80 --name my-container-23Q1 httpd"
			}
		}	
		stage ('deploy') {
			steps {
			sh " docker cp index.html my-container-23Q1:/usr/local/apache2/htdocs"	
			}
		}
	}
}
