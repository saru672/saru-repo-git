pipeline {
	agent {
	label "built-in"
	}
	stages {
		stage ('create container') {
		agent {
			docker {image 'httpd'}
		}
			steps {
			sh " docker run -itdp 80:80 --name my-container-2023Q1 httpd"
			}
		}	
		stage ('deploy') {
		agent {
		       docker {image 'httpd'}
		}
			steps {
			sh " docker cp index.html my-container-23Q1:/usr/local/apache2/htdocs"	
			}
		}
	}
}
