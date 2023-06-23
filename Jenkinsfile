node {
    docker.image('node:16-buster-slim').inside('-p 3000:3000') {
        stage('Test') { 
	    echo 'Hello' 
        }
	stage('Reset project settings') { 
	    sh 'rm -rf node_modules'
	    sh 'rm -rf package-lock.json'
	    sh 'npm cache clean --force'
        }
        stage('Build') { 
	    sh 'npm install' 
        }
    }
}
