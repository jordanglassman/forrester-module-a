node {
    properties([parameters([booleanParam(name: 'FAIL_BUILD', defaultValue: false, description: 'Force this build to FAILURE status'),
                            booleanParam(name: 'UNSTABLE_BUILD', defaultValue: false, description: 'Force this build to UNSTABLE status'),
                            booleanParam(name: 'ABORTED_BUILD', defaultValue: false, description: 'Force this build to ABORTED status')])])
    stage('checkout') {
        git url: 'https://github.com/jordanglassman/forrester-module-a.git'
    }
    if(${params.FAIL_BUILD}) {
        currentBuild.result = 'FAILURE'
        error('build failed due to FAIL_BUILD param setting')
    } else if(${params.UNSTABLE_BUILD}) {
        currentBuild.result = 'UNSTABLE'
        error('build failed due to UNSTABLE_BUILD param setting')
    } else if(${params.ABORTED_BUILD}) {
        currentBuild.result = 'ABORTED'
        error('build failed due to ABORTED_BUILD param setting')
    }
}
