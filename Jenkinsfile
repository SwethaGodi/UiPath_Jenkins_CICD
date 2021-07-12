pipeline {
    agent any

    stages {
        stage('Git') {
            steps {
                git branch: 'main', credentialsId: '411c23f6-fa32-43bb-bf63-c82a1adfd2ce', url: 'https://github.com/SwethaGodi/UiPath_Jenkins_CICD.git'
            }
        }
        stage('Build') {
            steps {
                echo "${WORKSPACE}"
                UiPathPack( outputPath: '${WORKSPACE}\\Output', projectJsonPath: 'project.json', version: CurrentVersion())
            }
        }
        stage('Deploy') {
            steps {
                UiPathDeploy( credentials: Token(accountName: 'mirackhaqfin', credentialsId: '0f936108-afeb-4292-bc61-f0b438f6999d'), environments: 'DevEnvironment', folderName: 'Default', orchestratorAddress: 'https://cloud.uipath.com/', orchestratorTenant: 'MiracleSoftwareSystemsDefault', packagePath: 'C:\\Users\\DELL\\AppData\\Local\\Jenkins\\.jenkins\\workspace\\UiPath_CICD_Pipeline_main\\Output')
            }
        }
    }
}

