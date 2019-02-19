pipeline {
	agent any

	tools{
		nodejs 'v10.15.1'
		npm '6.4.1'
	}

//	node {
//		checkout scm
//	}

	stages{
		stage('Build'){
			steps{
				echo 'node.js and npm version'
				sh 'nodejs --version'
				sh 'npm --version'
				sh 'npm install'
			}

		}
		stage('test'){
			steps{
				sh 'npm test'
			}
		}

		stage('Deploy'){
			when{
				expression{
					currentBuild.result == null || currentBuild.result == 'SUCCESS'
				}
			}
			steps {
				sh 'make publish'
			}

		}
	}
	
}
