pipeline {
	agent { label 'docker-agent' }
	stages {
		stage("Clone stage") {
			steps {
				git 'https://gitlab.com/tanchito/nodejs-todolist'
			}
		}
		stage("Build stage"){
			steps {
				sh label: '', script: 'docker build -t nodejs-todolist .'
				sh label: '', script: 'docker-compose up -d'
			}
		}
	}	
}
