pipeline {
	agent any

//	node {
//		checkout scm
//	}

	stages{
		stage('Build'){
			steps{
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
