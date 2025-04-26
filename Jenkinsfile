pipeline {
    agent any

    stages {
        stage('w/o docker') {
            steps {
                sh '''
					echo "Without docker "
					ls -la
					touch containerno.txt
				'''
            }
        }
        
        stage('w/ docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh '''
					echo "With docker "
					npm --version
					ls -la
					touch containerno.txt
					'''
            }
        }
    }
}
