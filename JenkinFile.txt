pipeline {
  agent any
  environment {
      MAJOR = '1'
      MINOR = '0'
	//Orchestrator Services
	UIPATH_ORCH_URL = "https://cloud.uipath.com/"
	UIPATH_ORCH_LOGICAL_NAME = "mirackhaqfin"
	UIPATH_ORCH_TENANT_NAME = "MiracleSoftwareSystemsDefault"
	UIPATH_ORCH_FOLDER_NAME = "Default"
  }
  stages {
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
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }    
    }
}
