pipeline {
	agent { label 'docker-agent' }
	stages {
		stage("Clone stage") {
			steps {
				#git 'https://gitlab.com/tanchito/nodejs-todolist'
				git 'https://github/peanutnbt/nodejs-todolist'
			}
		}
		stage("Build stage"){
			steps {
				sh label: '', script: 'docker build -t nodejs-todolist .'
				sh label: '', script: 'docker-compose up -d'
			}
		}
	}
	post{
		always{
			emailext body: '${DEFAULT_CONTENT}', subject: 'Jenkins CI/CD Notification', to: 'nbaotan98@gmail.com'
		}
	}	
}
