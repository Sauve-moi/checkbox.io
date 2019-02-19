pipeline {
	agent any

	tools{
		nodejs "Nodejs10"	
	}

//	node {
//		checkout scm
//	}

	stages{
		stage('Build'){
			steps{
				dir('/Users/Shared/Jenkins/Home/workspace/checkbox.io/server-side/site')
				{
					echo 'node.js and npm version'
	//				sh 'nodejs --version'
					sh 'npm --version'
					sh 'npm install'
				}
				
			}

		}
		stage('test'){
			steps{
				dir('/Users/Shared/Jenkins/Home/workspace/checkbox.io/server-side/site')
				{
					sh 'npm test'
				}
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
