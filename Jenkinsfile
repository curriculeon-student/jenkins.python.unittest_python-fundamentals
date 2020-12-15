timestamps {
node () {
	stage ('jenkins-python-integration - Checkout') {
 	 checkout([$class: 'GitSCM',
 	 branches: [[name: '*/master']],
 	 doGenerateSubmoduleConfigurations: false,
 	 extensions: [],
 	 submoduleCfg: [],
 	 userRemoteConfigs: [[credentialsId: '',
 	 url: 'https://github.com/simulationpoint/exercise.python_fundamentals.git']]])
	}
	stage ('jenkins-python-integration - Build') {
 			// Shell build step
powershell """
python -m unittest discover -s ./src/test/ -p '*_test.py'
 """
	}
}
}
