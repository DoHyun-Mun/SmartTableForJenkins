@Library('piper-lib-os') _

node() {
    stage('prepare') {
        deleteDir()
        checkout scm
        setupCommonPipelineEnvironment script:this
    }
    stage('build') {
        mtaBuild script: this
    }
    stage('deploy') {
        cloudFoundryDeploy script: this
    }
    stage('tmsupload') {
        tmsUpload script: this
    }
}