pipeline {
	agent any
	
	triggers {
	  cron 'H * * * *'
	}
	
	stages {
		stage('Get Public'){
			steps {
				sh """
					curl http://ipinfo.io/ip > my-public-ip.txt'
				"""
			}
		}
	}
	
	post {
		always {
			archiveArtifacts artifacts: 'my-public-ip.txt', followSymlinks: false
		}
	}
}