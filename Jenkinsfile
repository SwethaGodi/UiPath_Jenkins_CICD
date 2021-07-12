pipeline {
    agent any

    stages {
        stage('Git-checkout') {
            steps {
                git branch: 'main', credentialsId: '346437b0-29b5-4f12-a78f-7926df5cf35f', url: 'https://github.com/SwethaGodi/UiPath_Jenkins_CICD.git'
            }
        }
         stage('Build') {
            steps {
                UiPathPack( outputPath: '${WORKSPACE}\\Output', projectJsonPath: '${WORKSPACE}', version: CurrentVersion())
            }
        }
        stage('Deploy') {
            steps {
                UiPathDeploy credentials: Token(accountName: 'mirackhaqfin', credentialsId: '4510e6d2-333e-4044-a826-bf9909ab2d88'), environments: 'DevEnvironment', folderName: 'Default', orchestratorAddress: 'https://cloud.uipath.com/', orchestratorTenant: 'MiracleSoftwareSystemsDefault', packagePath: 'C:\Users\DELL\AppData\Local\Jenkins\.jenkins\workspace\UiPath_CICD_Pipeline_main'
            }
        }
    }
}
