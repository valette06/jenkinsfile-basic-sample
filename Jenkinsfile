node {
 	// Clean workspace before doing anything
    deleteDir()

    try {
        stage ('eric') {
        	checkout scm
        }
        stage ('yoly') {
        	sh "echo 'shell scripts to build project...'"
        }
        stage ('vals') {
	        parallel 'static': {
	            sh "echo 'shell scripts to run static tests...'"
	        },
	        'unit': {
	            sh "echo 'shell scripts to run unit tests...'"
	        },
	        'integration': {
	            sh "echo 'shell scripts to run integration tests...'"
	        }
        }
      	stage ('Deploy') {
            sh "echo 'shell scripts to deploy to server...'"
      	}
    } catch (err) {
        currentBuild.result = 'FAILED'
        throw err
    }
}




