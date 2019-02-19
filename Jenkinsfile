pipeline {
    agnet any
    
    tools {
        nodejs "Nodejs10"
        jdk "jdk8"
    }
    
    stages {
        stage('Demo') { 
            steps {
                echo "check npm && java version"
                sh "npm --version"
                sh "java -version"
            }
        }
    }
}
