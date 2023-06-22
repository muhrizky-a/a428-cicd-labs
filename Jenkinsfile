pipeline {
    agent {
        docker {
            image 'node:16-buster-slim' 
            args '-p 3000:3000' 
        }
    }
    stages {
        stage('Reset project settings') { 
            steps {
		sh 'rm -rf node_modules'
                sh 'rm -rf package-lock.json'
                sh 'npm cache clean --force'
            }
        }
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
    }
}
