pipeline {
    agent any

    stages {
    	stage('Checkout ClintWin source') {
	        steps {
	            git branch: 'master',
	                url: 'https://github.com/clintwin360/ClinTwin360_Web'
	            sh "ls -lat"
	        }
	    }
    	stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Package') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}