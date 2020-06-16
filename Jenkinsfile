pipeline {//1

    agent none
    environment {
            // tools
            MAVEN_TOOL = "maven3"
        }

      tools {
            maven MAVEN_TOOL
        }
    stages {//2
        stage("build"){//3
            agent any
            steps{//4
                sh 'mvn --show-version clean '
               // sh 'mvn --show-version --batch-mode --errors --no-transfer-progress -Dmaven.test.failure.ignore=true -Dspotbugs.failOnError=false  clean verify'
               // junit '**/target/surefire-reports/TEST-*.xml'
               // recordIssues(tool: spotBugs(), qualityGates: [[threshold: 1, type: 'TOTAL', unstable: true]])
                echo 'Helo " $PATH'
                sh 'ls -ls'

            }//4
        }//3
    }//2
}//1