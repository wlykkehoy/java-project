pipeline {
    agent {label "linux"}

    stages {
        stage("Unit Tests") {
            steps {           
                sh "ant -f test.xml"
                junit "reports/result.xml"
            }
        }
        stage("Build") {
            steps {
                sh "echo Hello from Build!"
            }
        }
        stage("Deploy") {
            steps {
                sh "echo Hello from Deploy!"
            }
        }
        stage("Report") {
            steps {
                sh "echo Hello from Report!"
            }
        }
    }
}


