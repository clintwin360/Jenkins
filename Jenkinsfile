pipeline {
    agent any

    stages {
    	stage('Checkout ClintWin source') {
	        steps {
	            git branch: 'master',
	                url: 'https://github.com/clintwin360/ClinTwin360_Web'
                sh "chmod +x ${WORKSPACE}/backup.sh"    
                sh "${WORKSPACE}/backup.sh"
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

    post {
        always {
            script {
                String buildResult = currentBuild.currentResult;   
                
                if ( buildResult == "SUCCESS" ) {
                    slackSend color: "good", message: "Job: ${env.JOB_NAME} with buildnumber ${env.BUILD_NUMBER} was successful"
                }
                else if( buildResult == "FAILURE" ) { 
                    slackSend color: "danger", message: "Job: ${env.JOB_NAME} with buildnumber ${env.BUILD_NUMBER} was failed"
                }
                else if( buildResult == "UNSTABLE" ) { 
                    slackSend color: "warning", message: "Job: ${env.JOB_NAME} with buildnumber ${env.BUILD_NUMBER} was unstable"
                }
                else {
                    slackSend color: "danger", message: "Job: ${env.JOB_NAME} with buildnumber ${env.BUILD_NUMBER} its resulat was unclear" 
                }
            }
        }
    }
}