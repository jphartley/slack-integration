pipeline {

    agent none

    stages {
        stage("build"){
            agent any
            steps{
                sh 'mvn --show-version --batch-mode --errors --no-transfer-progress -Dmaven.test.failure.ignore=true -Dspotbugs.failOnError=false  clean verify'
                 junit '**/target/surefire-reports/TEST-*.xml'
                    recordIssues(
                           tool: spotBugs(), qualityGates: [[threshold: 1, type: 'TOTAL', unstable: true]]
                )
            }
        }
    }
}
