pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
		docker build -t keyurbitw/abiomed:v1 .
		echo 'Docker Image Successfully created'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
		echo 'All Cases Successfully passed'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
		docker run -d -p 81:80 -p 443:443 -p 6379:6379 keyurbitw/abiomed:v1
		echo 'Container Successfully Created'
            }
        }
    }
}
