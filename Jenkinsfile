node {
    stage ('checkout') {
        checkout scm
    }
    stage ('build') {
        withMaven(maven: 'Maven350') {
            sh "mvn clean install"
        }
    }
    stage ('fingerprint') {
        archiveArtifacts artifacts: "target/*.jar", fingerprint: true
    }
    
    devOpticsConsumes jobName: 'schott-bug-bash/mean-lead-time-demo/master'
}
