pipeline{
	agent any

	parameters{
		booleanParam(name: "RUN_INTEGRATION_TESTS", defaultValue: true)
	}
	
	stages {
		stage('Test'){
			parallel {
				stage('Integration tests'){
					when {
						expression { return params.RUN_INTEGRATION_TESTS }
					}
					steps {
						// there were no steps, that's why the syntax error
						echo 'running integration tests'
					}
				}
				stage('Unit Tests'){
					steps {
						sh './mvnw test -D testGroups=unit'
					}
				}
			}
		}
	}
}
