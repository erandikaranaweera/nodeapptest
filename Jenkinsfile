pipeline{
	
	agent {label 'windows'}

	environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub')
	}
	
	stages {
	    
	    stage('gitclone') {

			steps {
				git 'https://github.com/erandikaranaweera/nodeapptest'
			}
		}

		stage('Build') {

			steps {
				sh 'docker build -t erandiranaweera/nodeappp:latest .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo 906210052errDd | docker login -u  erandiranaweera -p 906210052errDd '
			}
		}

		stage('Push') {

			steps {
				sh 'docker push erandiranaweera/nodeappp:latest'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}

}
