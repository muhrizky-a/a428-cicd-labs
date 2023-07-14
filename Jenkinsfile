node {
    docker.image('node:16-buster-slim').inside('-p 3000:3000') {
	stage('Reset project settings') { 
	    sh 'rm -rf node_modules'
	    sh 'rm -rf package-lock.json'
	    sh 'npm cache clean --force'
        }
        stage('Build') { 
	    sh 'npm install' 
        }
        stage('Test') { 
	    sh './jenkins/scripts/test.sh'
        }
        stage('Deploy') { 
	    sh './jenkins/scripts/deliver.sh'
	    input message: 'Sudah selesai menggunakan React App? (Klik "Proceed" untuk mengakhiri)'
	    sh './jenkins/scripts/kill.sh' 
        }
    }
}
