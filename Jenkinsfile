@Library('piper-lib-os') _

fioriOnCloudPlatformPipeline script:this
mtaBuild script: this

node() {
    stage('prepare') {
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('build') {
        mtaBuild script: this
    }
    stage('deploy') {
        cloudFoundryDeploy script: this
    }
}