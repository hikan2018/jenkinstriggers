pipeline {
	agent any
	stages {
	   stage('Build') {
	      steps{
	         sh 'echo "Build completed and success."'
	      }
	   }

	}
	post {
        always {
            echo 'Slack Notifications.'
            slackSend channel: '#learning',
                color: COLOR_MAP[currentBuild.currentResult],
                message: "*${currentBuild.currentResult}:* Job ${env.JOB_NAME} build ${env.BUILD_NUMBER} \n More info at: ${env.BUILD_URL}"
        }
    }
}
