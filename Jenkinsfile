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
                sh "ant -f build.xml -v"
            }
        }
        stage("Deploy") {
            steps {
                sh "echo Hello from Deploy!"
                sh "ls -la"
            }
        }
        stage("Report") {
            steps {
                sh "echo Hello from Report!"
            }
        }
    }
}


