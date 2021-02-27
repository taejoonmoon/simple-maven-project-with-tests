node('master') {
    checkout scm
    // some block
    stage('build') {
        withMaven(maven: 'M3')
        // some block
        sh "mvn -Dmaven.test.failure.ignore=true clean package"
    }

    stage('post') {
        junit '**/target/surefire-reports/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
    }
}
